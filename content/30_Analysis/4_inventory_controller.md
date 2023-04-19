---
title: "Inventory Controller"
chapter: true
weight: 4
---

![vFunction Logo](/images/vFunction.png)

### Inventory Controller

Moving on to the InventoryController service

1. In the services view of the analysis page, locate and open InventoryController

2. Click VIEW next to Dynamic classes to review the dynamic analysis results. There are two exclusive classes and one non-exclusive class (InventoryService)

3. Click on Details of the non-exclusive InventoryService class. You can see that ProductController is also using it.

4. Scroll down in the Details popup and click on ProductService.getProductInventory(), the call tree will open as shown as below:

    | ![Inventory-Controoler-Calltree](/images/Inventory-Controller-Calltree.png) |
    | :--: |
    | Product Service calling Inventory Service |
 
5. The call tree shows the ProductController is calling the InventoryService class, which is the service class of InventoryController service. Technically we can either merge the two services into one service (we will do this later for the Payment services, or we can create a new entry point in InventoryController for ProductController to access as a client. Since both services represent distinct functional domains, we will choose the second option.

6. In the call tree, click on the InventoryService$$EnhancerBySpringCGLIB.fetchInventory() node, click MAKE ENTRY POINT, select InventoryController and click MAKE.

    | ![Inventory-Controoler-Calltree](/images/Creating-EP.png) |
    | :--: |
    | Creating an Entry Point in the call tree |

7. Click Back to Services. The InventoryController service should be completely exclusive (including static and resources)
![vFunction Logo](/images/vFunction.png)
