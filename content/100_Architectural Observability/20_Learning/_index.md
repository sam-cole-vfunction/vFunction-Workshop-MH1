---
title: "Learning"
chapter: true
weight: 120
---

![vFunction Logo](/images/vFunction.png)

# Learning


In this part, you will run the OMS application and run a script that invokes the OMS APIs.

While the application is running, vFunction collects the data required for analyzing the application.

This process is called **Learning**, and the result is called **Measurement**.

1. In the vFunction server UI (same screen in the *"workshop-win"* VM shown at the end of the setup environment section), click START LEARNING

    ![start learning 1](/images/OMS-Learning-1.png)

2. Wait until vFunction starts collecting data from the controller

    ![start learning 2](/images/OMS-Learning-2.png)

3. Go to the PuTTY terminal connected to the Workshop Linux VM and do the following commands:

   ```text
   cd ~/oms-test-script/
   for i in `seq 1000`; do ./use-apis.sh ; sleep 0.5; done
   ```
5. In the vFunction Server Web UI (switch back to the Windows VM) - you should see the numbers of functions, resources and services in the WebUI go up after some time

6. Stop the Learning by clicking STOP in vFunction Web UI. We will use a ready measurement to save time

7. Stop the loop calling use-apis.sh in the "*workshop-linux*" VM (press Ctrl+C)

We've seen how to start the Learning process in which vFunction collects data from a running application.
The following section covers how to analyze the data and specify services.


{{% notice note %}}
The OMS application is deployed on a tomcat server on the Linux machine located at /opt/tomcat/latest/.
To stop tomcat do: **sudo bash /opt/tomcat/apache-tomcat-9.0.56/bin/shutdown.sh** (or simply kill the process)
To start tomcat do: **sudo bash /opt/tomcat/apache-tomcat-9.0.56/bin/startup.sh**
{{% /notice %}}

![vFunction Logo](/images/vFunction.png)
