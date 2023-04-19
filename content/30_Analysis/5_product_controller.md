---
title: "Product Controller"
chapter: true
weight: 5
---

![vFunction Logo](/images/vFunction.png)

### Product  Controller

1. Select the ProductController service; notice that its sphere has an arrow pointing to the InventoryController service because of the entry point we added in the previous section. Hovering over that line shows the method we marked as the new entry point. The Dynamic exclusivity of ProductController is already 100%.

2. Let’s view the static analysis result as we did before. The two non-exclusive classes are ShippingRespository and ShippingService.

3. The ShippingService is the service class of the ShippingController in the monolith (like the InventoryService being the service class of InventoryController). Since we only see ShippingService in the static analysis, none of the flows covered in the dynamic analysis detected a call to this class. Assuming the coverage of our flows is sufficient, we conclude that the code using this class is “dead code” and should be excluded from (refactored out) of the extracted service.
To do that, select ShippingService (non-exclusive class) and click MARK AS DEAD-CODE. The class is listed under DEAD-CODE section for this service. When we will extract this service (in the next part of this lab), references to this class will be removed.

4. Once the analysis is completed, the static exclusivity of ProductController is 100% - the ShippingRespository is also removed from this service. The reason for that is that the dependency on ShippingRepository originated from the dependency on ShippingService.

5. Switching to view the resources of ProductController and looking at the non-exclusive resources, we see that this service uses three database tables that are also used by other services. This is expected, and we don’t need to do anything.

6. Go Back to Services

![vFunction Logo](/images/vFunction.png)
