---
title: "Inventory Controller"
chapter: true
weight: 4
---

![vFunction Logo](/images/vFunction.png)

### Inventory Controller

Moving on to the InventoryController domain

1. In the domains view of the analysis page, locate and open InventoryController

2. Click VIEW next to Dynamic classes to review the dynamic analysis results. There are two exclusive classes and one non-exclusive class (InventoryService)

3. Click on Details of the non-exclusive InventoryService class. You can see that ProductController is also using it.

4. Scroll down in the Details popup and click on ProductService.getProductInventory(), the call tree will open as shown as below:

    | ![Inventory-Controoler-Calltree](/images/Inventory-Controller-Calltree.png) |
    | :--: |
    | Product Domain calling the InventoryService class |
 
5. The call tree shows the ProductController is calling the InventoryService class, which is the service class of InventoryController domain. Technically we can either merge the two domains into one domain (we will do this later for the Payment domains, or we can create a new entry point in InventoryController for ProductController to access as a client. Since both domains represent distinct functional domains, we will choose the second option.

6. In the call tree, hover over the InventoryService$$EnhancerBySpringCGLIB.fetchInventory() node, click MAKE ENTRY POINT, then METHOD, check InventoryController and click MAKE.

    | ![Inventory-Controoler-Calltree](/images/Creating-EP.png) |
    | :--: |
    | Creating an Entry Point in the call tree |

7. Click Back to domains. The InventoryController service should be completely exclusive (including static and resources)
![vFunction Logo](/images/vFunction.png)
