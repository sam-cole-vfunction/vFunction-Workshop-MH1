---
title: "Appendix: AWS Refactor Spaces"
chapter: true
weight: 70

---
![vFunction Logo](/images/vFunction.png)

# Appendix: Using AWS Refactor Spaces to "Strangle" the OMS Monolith

Strangler Pattern is used for incremental migration from a legacy monolith to services by replacing existing functionalities provided by the monolith with functionalities provided by the services. 

AWS Migration Hub Refactor Spaces is a tool that allows one to automate and manage this incremental migration by creating and configuring an elastic load balancer in AWS that routes API calls either to the monolith or to the relevant service.

In this appendix, you will use Refactor Spaces to strangle the example OMS application after it was refactored in vFunction, and three of the services were deployed to EKS.


### Precondition: Test that the monolith works via the public IP address

1. In the Windows VM, open Postman

2. Import to postman the file: **C:\vFunctionLab\oms-tutorial\oms-webmvc\script\OMS.postman_collection.json**

3. In the **OMS** Collection, open *Create Order* and change localhost with the public IP of the Linux machine

4. Send the request and ensure you get a correct response


### Create Environment

1. Open the AWS console of one of the EC2 instances of the workshop VMs and copy the VPC ID for the next steps

2. Search and open the Refactor Spaces feature of AWS Migration Hub (same region as the workshop)

3. On the left pane, click on *Environments* and then click *Create environment* in the main pane

    ![RefSpace1-Environments-Page](/images/RefSpace-1-Environemnts-Page.png)    

4. In the *Create environment* form, set the Environment name to **Workshop-OMS** and hit Next

5. In the *Create application* form, enter **Order Management System** for the application name

6. Select the VPC ID of the workshop VPC

7. Click Next in the *Share environment - optional*

8. Review and Create the environment

### Create Service with Default Route

1. After the environment on the Environments page is shown to be in the Healthy state, click on the environment and then on the Order Management System application. 

2. Create a service based to which the messages will be routed to by default:

    a. Set the service name to OMS-Monolith

    b. Set the VPC to the VPC of the workshop (as before)

    c. The default route Endpoint should redirect the traffic to the monolith running on the Linux machine, so it should be in the form: http://[Linux VM public IP]:8080/oms-0.0.1-SNAPSHOT/service

    d. Check the checkbox for the default route

3. The application screen should look similar to:

    ![Post Def Service Creation](/images/RefSpace2-DefaultServiceResult.png)

### Create Service for Order Controller

1. In the Order Management Application Screen, click Create Service

2. Set the *Service name* to **order-controller**

3. Set the VPC to the VPC of the workshop (as before)

4. Set the endpoint to the endpoint of order controller in EKS - the endpoints used in the [Deployment](/50_deployment/_index.aws.html) section (e.g., http://a607a6d36a4cf497b86eeedc239dcb91-fe444a9b3f77e2b5.elb.us-west-2.amazonaws.com/order-controller)

5. Click Create service

6. Click *Create Route* and set the *Source path* to **/order-controller**, then click *Create route*. The example form is below:
    ![Create Route Order Controller](/images/RefSpace3-CreateRoute.png)

7. The application screen should now look similar to:

    ![Ref Spaces Configured](/images/RefSpace4-Configured.png)

### Test

Copy the Proxy URL of the Order Management System application in Refactor Spaces and use it to call APIs by replacing it in Postman

Example: For a Proxy URL https://gv4qtsettk.execute-api.us-west-2.amazonaws.com/prod

1. https://gv4qtsettk.execute-api.us-west-2.amazonaws.com/prod/order-controller/order/multi to create multiple order by routing the calls to EKS

2. https://gv4qtsettk.execute-api.us-west-2.amazonaws.com/prod/inventory  sends the API call to the monolith to create an inventory item

    ![Postman screenshot](/images/RefSpace5-Postman.png)

### Cleanup

Before proceeding to the [Cleanup](/60_cleanup/_index.aws.html) section, make sure to delete the Refactoring Spaces environment. You will need first to delete the routes and services, then the application and finally the environment.

![vFunction Logo](/images/vFunction.png)
