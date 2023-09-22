---
title: "Update OMS"
chapter: true
weight: 2
---

![vFunction Logo](/images/vFunction.png)

### Change the OMS Application

In this section we will clone the OMS public git repo, switch to the updated branch and then configure and deploy the new version. 

The modified version of OMS adds managing customers. 

All the commands are done on the Linux machine, i.e., open PuTTY as you've done in the [Setup Environment](/10_setup/_index.aws.html) section and login to the Linux VM. 


1. Install git

```bash
sudo yum install git
```

1. Install maven

```
sudo yum install maven
```

3. Clone code repo and checkout ao-demo-1 branch

```bash
cd ~
git clone https://workshop@bitbucket.org/vfunction/oms-tutorial.git
cd oms-tutorial
git checkout ao-demo-1
```

4. Update the DB properties

```bash
cd ~/oms-tutorial/oms-webmvc
sudo cp /opt/tomcat/latest/webapps/oms-0.0.1-SNAPSHOT/META-INF/context.xml ./app/src/main/webapp/META-INF/context.xml
```


5. Build the app

```bash
cd ~/oms-tutorial/oms-webmvc
mvn install
```

5. Deploy the application

```bash
sudo cp ./app/target/oms-0.0.1-SNAPSHOT.war  /opt/tomcat/latest/webapps/
```

6. Restart tomcat

```bash
sudo /opt/tomcat/latest/bin/shutdown.sh
sudo /opt/tomcat/latest/bin/startup.sh
```


7. Since the binaries changed, we need to restart the controller in order to restart viper (the process doing static analysis),
otherwise vFunction will notify that static analysis is missing classes and the architecture will be incorrect.

```bash
sudo cd /opt/vfunction/controller-installation
sudo bash restart-controller.sh
```

![vFunction Logo](/images/vFunction.png)