---
title: "Config Observation"
chapter: true
weight: 1
---

![vFunction Logo](/images/vFunction.png)

### Setting up automatic observation of architectural changes

1. Click on the OBSERVATION page. The first page (figure below) is used to configure which events should be triggered due to differences between the new measurement (auto learning) and the baseline. You can set the exclusivity threshold for the domain exclusivity event and you can enable to get mail and slack notifications when an automatic learning ends.

    ![Config Alerts](/images/ConfigAlerts.png)

2. Leave the *Configure Alerts* unchanged and click *Configure Plan*. Select "Baseline 1" as the base measurement - the events will be triggered by comparing the new measurement with "Baseline 1". You can optionally enable triggering starting and ending learning via scripts (useful for automatic learning as part of CI/CD pipelines) but we are not be covering that in this tutorial.

    ![Config Plan](/images/ConfigPlan.png)

3. Click on *Schedule Learning* and then on *Add New Schedule*. This page is used to time starting and ending of learning (note the server current time at the top right corner of the page). You must select the controllers for the learning. The Repeat sets the frequency of the learning (e.g., daily) while the Analysis can be set to a lower frequency (e.g., Weekly). Having a lower frequency of analysis means that the learning can continue to add data to the same measurement but only when the analysis will performed the new measurement events will be triggered and the measurement will become accessible for the user to review. In our case, we only have one controller - *oms-controller*.

We will configure and use schedule learning later - for now you can simply continue to the next page.

    ![Config Plan](/images/ConfigSchedLearning.png)


![vFunction Logo](/images/vFunction.png)