---
title: "Other Services"
chapter: true
weight: 7
---

![vFunction Logo](/images/vFunction.png)
### Shipping Price Controller and Modifying Fulfillment Controller

1. Select the ShippingPriceController domain – its dynamic class exclusivity is 50%

2. View the dynamic classes, the ShippingService is the non-exclusive class.

3. Click DETAILS to see what other services use this class (ShippingService) – it is also used by ModifyFulfillmentOrder.

4. In the pop-up, click on ModifyFulfillmentService.getShippingAmout() and move up the call tree to see the call tree as shown here:

    | ![Modify Fulfullment Calltree](/images/ModifyingFulfillment-Calltree.png) |
    | :--: |
    | Modify Fulfillment Calltree |

5. Make ShippingService$$EnhancerBySpringCGLIB.fetchShippingCharges() an entry point of ShippingPriceController - click on the node in the call tree, click MAKE ENTRY POINT, METHOD and select ShippingPriceController domain.

6. Go back to the domains view and wait for the analysis to complete. The ShippingPriceController is 100% class exclusive (static and dynamic)

7. Select the ModifyFulfillmentController; it has 100% dynamic class exclusivity and 33% static exclusivity. Review the non-exclusive classes – there are 3 DTO classes and one repository class – this seems fine, and we don’t need to change it.

8. Review the left pane of the Analysis Page. The analysis output shows 100% class exclusivity for 100% extracted percentage. This means we have reached a state in which we have eight services that are fully exclusive with respect to the testing flows performed in the Learning phase

    | ![Complete Analysis](/images/Complete-Analysis.png) |
    | :--: |
    | Complete Analysis |


![vFunction Logo](/images/vFunction.png)
