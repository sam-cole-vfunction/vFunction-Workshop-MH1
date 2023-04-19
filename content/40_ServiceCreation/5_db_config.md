---
title: "Service config. to use the DB"
chapter: true
weight: 5
---

![vFunction Logo](/images/vFunction.png)

### Reconfiguring the services data source from Spring MVC to Spring Boot

The original application is a Spring Web MVC application, using a MySQL database running in Tomcat via JNDI (Java Naming and Directory Interface). The configuration is specified in spring-config.xml (src/main/resources folder) of the original application.

To switch from the JNDI based Spring MVC configuration to the Spring Boot configuration, we will need to do three steps for each of the services:

1. Add a dependency to connect to MySQL DB to the **pom.xml** of the service

 ``` XML
 <dependency>
 <groupId>mysql</groupId>
 <artifactId>mysql-connector-java</artifactId>
 <scope>runtime</scope>
 </dependency>
 ```

2. **Delete** the XML elements **src/main/resources/META-INF/rr/spring-config.xml** in the resources/META-INF/rr directory (lines 9-39):

    Starting from:

    ``` XML
    <jdbc:initialize-database data-source="dataSource">
    <jdbc:script location="classpath:schema.sql"/>
    </jdbc:initialize-database>
    ```

    Ending with:
    ```XML

    <tx:annotation-driven proxy-target-class="true" transaction-manager="transactionManager"/>

    <bean class="org.springframework.orm.jpa.JpaTransactionManager" id="transactionManager">
    <property name="entityManagerFactory" ref="entityManagerFactory"/>
    </bean>

    ```

4. Connect to the **workshop-linux** VM running the original application, and view the DB config file:

    ```bash
    sudo less /opt/tomcat/latest/webapps/oms-0.0.1-SNAPSHOT/META-INF/context.xml
    ```

    The URL, username and password will be used in the next step.

4. Create an **application.properties** file under the folder **src/main/resources** with the following content:

    ``` properties
    spring.datasource.url=[url]
    spring.datasource.driver-class-name =com.mysql.cj.jdbc.Driver
    spring.datasource.username=[username]
    spring.datasource.password=[password]
    spring.jpa.hibernate.ddl-auto=update
    ```   
 
    Set the **url, username** and **password** (without the double quotes) according to the values in the application's context.xml above.
    
    The URL should start with jdbc:mysql and end with ?createDatabaseIfNotExist=true; the rest should be omitted.
    For example: 
    ```jdbc:mysql://workshop-mysql-o4o2kr.c6wk1jfk53qs.us-west-2.rds.amazonaws.com:3306/oms1?createDatabaseIfNotExist=true```
  
    **Make sure there are no white spaces after the values (e.g. for username and password)**


    We will fine-tune these properties for each service in the following sections.

{{% notice note %}}
If you get an error opening  .properties files in Eclipse, right click on the .properties file and open it in a text editor (Open With…->Text Editor)
{{% /notice %}}
![vFunction Logo](/images/vFunction.png)
