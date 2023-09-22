---
title: "AO Tutorial"
chapter: true
weight: 100
---

![vFunction Logo](/images/vFunction.png)


# Architectural Observability (AO) Tutorial

{{% notice note %}}
Please complete the [Setup Environment](/10_setup/_index.aws.html) section before starting the tutorial
and don't forget to [Cleanup](/300_cleanup/_index.aws.html) when you're done with the workshop
{{% /notice %}}


This is a hands-on tutorial for the vFunction Architectural Observability (AO) module. 

We will use the Order Management System (OMS) demo application to show how to collect, analyze, gain insights as well as monitor and handle architectural debt and architectural drifts of an application.


### Learning Objectives

- How to collect data for architectural observability
- How to identify and address architectural tech debt
- How to define and baseline domains for the application
- How to continuously monitor and address architectural drifts

### Workshop Flow

The following flowchart describes the tutorial steps and artifacts of this tutorial. 

The rounded rectangles represent steps you'll perform (with time estimation), the parallelograms represent artifacts / results (some can be downloaded) and the trapezoid represent an event.

{{<mermaid align="center">}}
graph TD;
    Learning(["Learning: Collecting data for architectural observability (10 min.)"])
    Learning --> Measurement[/"Initial Measurement (click to download)"/]
    Measurement --> Analysis(["Analysis: Get architectural insights and baseline functional domains (45 min.)"])
    Analysis --> BaselineDomains[/" Baseline measurement"/]
    BaselineDomains --> Obs(["Observation: Setup continuous monitoring of architectural drifts"])
    Obs --> AppMod(["Deploy and test a new version of the OMS app"])
    AppMod --> NewMeasurement[/"New measurement + todos"/]
    Obs -.-> SchedLearning[/"Scheduled Learning and Analysis"\]
    SchedLearning -.-> NewMeasurement
    NewMeasurement --> Review(["Review and handle todos"])
    
    click Setup "./10_setup/_index.aws.html"
    click Learning "./20_learning.html"
    click Analysis "./100_architectural-observability/30_analysis.html"
    click Obs "./100_architectural-observability/40_observation.html"
    click ServiceCreation "./40_servicecreation.html"
    click Deployment "./50_deployment/_index.aws.html"
    click Cleanup "./60_cleanup/_index.aws.html"


    click OMSApp "https://bitbucket.org/vfunction/oms-tutorial/src/mysql/oms-webmvc/" _blank
    click Measurement "https://portal.vfunction.com/file/eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1dWlkIjoiNWNhYmNjYTMtNTc5MC00MmY1LWE0ODgtM2RhODZmOGVjYzlmIn0.C--1C7PmFRGUxWxDe-hOtaA9PvmV8NiLLbHrmXmYEr0/5cabcca3-5790-42f5-a488-3da86f8ecc9f/Analysis-Tutorial-Start.zip"
    click ServiceSpecs "https://bitbucket.org/vfunction/oms-tutorial/src/mysql/oms-services/service-specs/" _blank
    click Services "https://bitbucket.org/vfunction/oms-tutorial/src/mysql/oms-services/" _blank
{{< /mermaid >}}

Click on the right arrow or Learning on the left pane to start

![vFunction Logo](/images/vFunction.png)