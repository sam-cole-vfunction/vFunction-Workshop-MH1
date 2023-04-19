---
title: "vFunction Modernization Workshop"
chapter: true
weight: 1
---

![vFunction Logo](/images/vFunction.png)

# vFunction AWS Modernization Workshop

### Welcome

vFunction is a cloud-native modernization platform that combines dynamic and static code analysis,
data science and automation to automatically identify and extract services from existing applications.

In this workshop, you will learn how to modernize a Java Spring application by refactoring it into Java Spring Boot Micro Services and deploying them into AWS Elastic Kubernetes Service (EKS).

### Learning Objectives

- How to modernize Java applications using vFunction
- In which cases vFunction can reduce efforts by orders of magnitude
- What manual efforts are involved in the modernization process
- Understand some of the best practices

### Who should attend?

* Application teams
* Architects
* Developers
* Technical Leads
* Operations Engineers
* Infrastructure teams

### Workshop Overview

The following flowchart describes the workshop flow with time estimations, links to the sections and example artifacts.

{{<mermaid align="center">}}
graph TD;
    Setup(["Setup: Setting up the AWS Environment and Installing vFunction (20 min.)"]) --> OMSApp[/"Deployed vFunction platform on AWS with the running Java monolith to be modernized (click to see Git)"/]
    OMSApp --> Learning(["Learning: Running the application and collecting data for vFunction analysis (10 min.)"])
    Learning --> Measurement[/"Measurement (click to download)"/]
    Measurement --> Analysis(["Analysis: Use vFunction to analyze and identify the services to be separated out of the application (45 min.)"])
    Analysis --> ServiceSpecs[/"Service Specs (click to see in Git)"/]
    ServiceSpecs --> ServiceCreation(["Service Creation: Create the independently deployable services (100 min.)"])
    ServiceCreation --> Services[/"Services (click to see in Git)"/]
    Services --> Deployment(["Deployment: Deploy the services to EKS (20 min.)"])
    Deployment --> KubeServices("Services Deployed in EKS")
    Deployment ---> Cleanup(["Cleanup: Delete all workshop resources from AWS (10 min.)"])

    click Setup "./10_setup/_index.html"
    click Learning "./20_learning.html"
    click Analysis "./30_analysis.html"
    click ServiceCreation "./40_servicecreation.html"
    click Deployment "./50_deployment/_index.html"
    click Cleanup "./60_cleanup/_index.html"

    click OMSApp "https://bitbucket.org/vfunction/oms-tutorial/src/mysql/oms-webmvc/" _blank
    click Measurement "https://portal.vfunction.com/file/eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1dWlkIjoiNWNhYmNjYTMtNTc5MC00MmY1LWE0ODgtM2RhODZmOGVjYzlmIn0.C--1C7PmFRGUxWxDe-hOtaA9PvmV8NiLLbHrmXmYEr0/5cabcca3-5790-42f5-a488-3da86f8ecc9f/Analysis-Tutorial-Start.zip"
    click ServiceSpecs "https://bitbucket.org/vfunction/oms-tutorial/src/mysql/oms-services/service-specs/" _blank
    click Services "https://bitbucket.org/vfunction/oms-tutorial/src/mysql/oms-services/" _blank
{{< /mermaid >}}

### To benefit the most from this workshop, you should know:

- Basic Java (we will use Eclipse for coding)
- Basic UNIX commands
- Basic AWS concepts



{{% notice warning %}}
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various AWS services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments.
{{% /notice %}}

![vFunction Logo](/images/vFunction.png)