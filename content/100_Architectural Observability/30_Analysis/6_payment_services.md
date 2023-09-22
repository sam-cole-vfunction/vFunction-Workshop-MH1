---
title: "Payment Domains"
chapter: true
weight: 6
---

![vFunction Logo](/images/vFunction.png)
### Payment Domains
1. Locate the two payment domains: PaymentService and DinersPaymentService. Looking at the spheres in the center pane, they are both being used by ModifyFulfillmentController.

2. Both domains have 50% exclusivity and consist of two classes. The non-exclusive class, AbstractPaymentHttpClient, is shared by both (select one of the domains, click on VIEW next to Dynamic classes, go to the Non-exclusive class, and click Details to see the services that are using it)

3. Let's merge these two domains into a single PaymentService. Go back to the domains screen, select the DinersPaymentService sphere, drag it on top of the PaymentService sphere and confirm the merge. Wait for the analysis auto-run to complete.

4. The resulting PaymentService has 100% dynamic exclusivity and 80% static class exclusivity. The non-exclusive classes are Data Transfer Object (DTO) classes which are also being used by the client service ModifyFulfillmentOrder. This is OK as it is part of the interface used between these two domains.
![vFunction Logo](/images/vFunction.png)
