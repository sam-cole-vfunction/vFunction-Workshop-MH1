---
title: "Automated Microservice Design with Modernization Hub"
chapter: true
weight: 1
---

![vFunction Logo](/images/vFunction.png)

# Automated Microservice Design with Modernization Hub

### Introduction

Transforming complex monolithic applications into microservices is the next major step in application modernization. Refactoring and re-architecting business critical applications will restore engineering velocity, lower costs, increase application scalability, and further unlock the value of the cloud. vFunction Modernization Hub automates and facilitates the actual decomposition process for developers and architects tasked with maintaining monoliths already lifted and shifted into the cloud or apps that are in the process of being moved and improved into AWS. 

### Learning Objectives

Focused on Java and .NET monoliths, this workshop will cover how to set up dynamic and static analysis that observes and analyzes architectures to identify and design microservices, splitting the monolith into domains with well-defined boundaries, high exclusivity, and APIs. vFunction Modernization Hub observes and identifies the key areas of architectural technical debt, pinpointing how to optimize microservice design, and extracting those microservices ready for cloud native deployment. 

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

### Requirements:

The workshop will deploy into an AWS account you have 3 choices

1) Use an existing funded AWS account
2) Create a new funded AWS account
3) If your attending an AWS hosted Event an AWS account will be provided - There will be no charges and AWS will cover all costs.

{{% notice warning %}}
If you deploy the workshop using your own AWS account you will be responsible for the costs incurred for using the AWS resources deployed by the workshop. These costs will continue until the resources are terminated/removed.
{{% /notice %}}

{{% notice warning %}}
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various AWS services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments.
{{% /notice %}}

![vFunction Logo](/images/vFunction.png)