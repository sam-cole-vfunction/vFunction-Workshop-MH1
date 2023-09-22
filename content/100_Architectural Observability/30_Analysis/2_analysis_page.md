---
title: "Analysis page walkthrough"
chapter: true
weight: 2
---

![vFunction Logo](/images/vFunction.png)

### Analysis page walkthrough

Let's walk through the analysis page and understand the basics.


- The center pane shows spheres representing the domains. The sphere's size is proportional to the number of classes it includes. The color represents its exclusivity – the percentage of classes that are only used by the domain itself (exclusive to the domain). We will elaborate more on exclusivity later. The dashed arrows between spheres represent calls across domains.
 The calls can be seen when hovering over the arrows.

- At the top of the center pane, we see four hyperlinks to navigate between the phases (Learning, Analysis, Observation and Service Creation). Every time a change is made to the domains during the analysis, the blue line under the Analysis label will show the progress of the auto-analysis run.

- The magnifying glass icon at the top right is used for doing a string-based search.

- Next to the search we have a bell icon with a number showing a number. This icon is used to open notification for the user and number is the number of notifications. Currently, if you click on this icon you should see one notification that the learning results include beans and DB tables.

![Analysis Start](/images/OMS-Analysis-1.png)

- At the bottom of the central pane, there is a menu labeled MEASUREMENTS which has various actions related to measurements such as selecting, importing, downloading, creating a snapshot, etc.

- The left pane has several sections:

  - Analysis Output: provides a summary of the current analysis status, such as the total no. of domains, entry points, etc., and a summary of the total exclusivity measure of the domains.
  
  - Actions: a set of actions concerning the entire analysis, for example, configuring the analysis parameters, showing resource report, etc.
  
  - A legend that includes a histogram showing the number of domains for each level of exclusivity.

- The right pane lists all the domains. It has a filter field at the top to filter domains by name. Selecting a domain in the list also selects the corresponding sphere (and vice versa). Hovering over a sphere in the center pane will highlight the domain on the right pane.

- Also on the right pane, there is a second tab labeled "High Debt" where architecturally high-debt classes are listed. In our case, OMS is a very simple application, so if you click on that tab you will just see ProductController, and even this class has a debt score of 3.1 out of 10.

![vFunction Logo](/images/vFunction.png)
