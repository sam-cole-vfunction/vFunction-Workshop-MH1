---
title: "Analysis page walkthrough"
chapter: true
weight: 2
---

![vFunction Logo](/images/vFunction.png)

### Analysis page walkthrough

Let's walk through the analysis page and understand the basics.


- The center pane shows spheres representing the services. The sphere's size is proportional to the number of classes it includes. The color represents its exclusivity – the percentage of classes that are only used by the service itself (exclusive to the service). We will elaborate more on exclusivity later. The dashed arrows between spheres represent calls across services.
 The calls can be seen when hovering over the arrows.

- At the top of the center pane, we see four hyperlinks to navigate between the phases (Learning, Analysis, Service Creation and Modernized). Every time a change is made to the services during the analysis, the blue line under the Analysis label will show the progress of the auto-analysis run.

- The magnifying glass icon at the top right is used for doing a string-based search.

![Analysis Start](/images/Analysis-Start.png)

- There are three actions at the bottom of the central pane for performing a new measurement (Learning), importing a previously downloaded analysis measurement, or selecting a previous analysis measurement.

- The left pane has several sections:

  - Analysis Output: provides a summary of the current analysis status, such as the total no. of services, entry points, etc., and a summary of the total exclusivity measure of the services.
  
  - Actions: a set of actions concerning the entire analysis, for example, configuring the analysis parameters, downloading the measurement, showing resource report, etc.
  
  - A legend that includes a histogram showing the number of services for each level of exclusivity.

- The right pane lists all the services. It has a search field at the top to filter services by name. Selecting a service in the list also selects the corresponding sphere (and vice versa). Hovering over a sphere in the center pane will highlight the service on the right pane.

![vFunction Logo](/images/vFunction.png)
