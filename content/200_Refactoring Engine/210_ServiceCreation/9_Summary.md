---
title: "Summary"
chapter: true
weight: 9
---

![vFunction Logo](/images/vFunction.png)

### Summary

We demonstrated how vFunction simplifies and expedites extracting running independent services from the original application code into spring-boot services.

We started by downloading the specification files from vFunction.

Then we used code-copy to extract and build the common library as the infrastructure jar for the services.

We then described the details to extract, build, run and test three services: OrderController, InventoryController and ProductController. All three services share a MySQL DB. ProductController also requires implementing a service-to-service call, since it uses the API of InventoryController for some of its queries.

![vFunction Logo](/images/vFunction.png)
