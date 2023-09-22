---
title: "Product Controller"
chapter: true
weight: 5
---

![vFunction Logo](/images/vFunction.png)

### Product  Controller

1. Select the ProductController domain; notice that its sphere has an arrow pointing to the InventoryController domain because of the entry point we added in the previous section. Hovering over that line shows the method we marked as the new entry point. The Dynamic exclusivity of ProductController is already 100%.

2. Let’s view the static analysis result as we did before. The two non-exclusive classes are ShippingRepository and ShippingService.

3. The ShippingService is the service class of the ShippingController (like the InventoryService being the service class of InventoryController). Since we only see ShippingService in the static analysis, none of the flows covered in the dynamic analysis detected a call to this class. Assuming the coverage of our flows is sufficient, we conclude that the code using this class is “dead code” and should be excluded from (refactored out) of the extracted domain.
To do that, select ShippingService (non-exclusive class) and click MARK AS DEAD-CODE. The class is listed under DEAD-CODE section for this domain. When we will extract this service (Refactoring Engine Tutorial), references to this class will be removed.

4. Once the analysis is completed, the static exclusivity of ProductController is 100% - the ShippingRespository is also removed from this domain. The reason for that is that the dependency on ShippingRepository originated from the dependency on Shippingdomain.

5. Switching to view the resources of ProductController and looking at the non-exclusive resources, we see that this domain uses three database tables that are also used by other domains. This is expected, and we don’t need to do anything.

6. Go Back to Domains

![vFunction Logo](/images/vFunction.png)
