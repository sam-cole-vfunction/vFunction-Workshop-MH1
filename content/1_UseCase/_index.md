---
title: "Use Case"
chapter: true
weight: 1
---

![vFunction Logo](/images/vFunction.png)

## Use Case

CoffeeShippingCo has a **legacy Monalithic Java application** ‘Order Management System’ running in its on premiss datacentre. It was originally created **20 years ago by a former employee** and has undergone a number of **changes and upgrades** as the business has evolved. Its now a Java Spring application running under tomcat with a MySQL database backend. The application is still being developed by CoffeeShippingCo with a release every quarter. This is because of the detailed testing needed to avoid any production outages as the application has become **complex over time**.

CoffeeShippingCo has just won a large contract with a major retailer and has concerns over the **scalability** of the ‘Order Management System’ to meet the increased demand. The new contract requires CoffeeShippingCo to increase the releases to Monthly.

### Challenges:

1)	Application Scalability
2)	Slow Engineering velocity due to a build-up on technical debt in the application

### Solution:

Refactor the application into a Microservices Architecture. This will enable scalability and simplify the software development and release process to meet the new requirements.

CoffeeShippingCo have decided to use Amazon EKS to run the Micro Services as containers and Amazon RDS for the database backend.

We will use vFunction Modernisation Hub to automate the refactoring of the application into micro services and deploy the new services into AWS



![vFunction Logo](/images/vFunction.png)
