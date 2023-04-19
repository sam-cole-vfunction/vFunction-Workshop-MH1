---
title: "Order Controller"
chapter: true
weight: 6
---

![vFunction Logo](/images/vFunction.png)

{{% notice info %}}
Pasting double quotes to Eclipse Java editor may result in smart quotation causing compilation errors. In this case, you need to change them to neutral double quotes
{{% /notice %}}


### Order Controller

1. Go to the OrderController project in Eclipse, and configure the DB as described in section [Reconfiguring the services data source from Spring MVC to Spring Boot](/40_servicecreation/5_db_config.html) 

2. Edit the class **com.oms.ordercontroller.OrderControllerApp.java** 

3. Add the annotation ```@EntityScan(basePackages = { "com.oms.entity" })``` (ensure the double quotes are copied correctly - see above note)

4. Add the requirement import statement (```import org.springframework.boot.autoconfigure.domain.EntityScan; ```)

5. The file should be similar to the below (the added lines are marked //added):

    ``` java
    package com.oms.ordercontroller;

    import org.springframework.boot.SpringApplication;
    import org.springframework.boot.autoconfigure.SpringBootApplication;
    import org.springframework.context.annotation.ImportResource;
    import org.springframework.boot.autoconfigure.domain.EntityScan; // added

    @SpringBootApplication
    @ImportResource({"spring-config.xml"})
    @EntityScan(basePackages = { "com.oms.entity" }) // added
    public class OrderControllerApp {
            public static void main(String[] args)
            {
                SpringApplication.run(OrderControllerApp.class, args);
            }
    }
    ```

3. Compile the service by doing *Maven clean* and *Maven install* using the context menu of the project or pom.xml file

4. Run the service as a *Spring Boot App* using the context menu of the project

    ![Run-SBApp](/images/Run-SBApp.png)

5. Open postman, if prompted to create an account or sign, click Skip and go to the app (at the bottom)

6. If the collections are empty, import the *OMS Services* collection from the oms-tutorial repo:

    a. Do File->Import... (or click Ctrl+O)

    b. Click Upload Files

    c. Navigate to *C:\vFunctionLab\oms-tutorial\oms-services* and double click on **'OMS Services.postman_collection'**
 
    d. Click Import

5. Open Postman, go to the Orders folder in OMS Services, then review and run the requests Create Order, Create Multiple Orders and Get Order By ID. You should see responses as below:

    | ![Postman Order Controller](/images/Postman-Order-Controller-Win.png) |
    | :--: |
    | Screenshot of using Postman to test Order Controller |


![vFunction Logo](/images/vFunction.png)
