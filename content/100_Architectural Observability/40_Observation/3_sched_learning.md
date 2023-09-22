---
title: "Scheduled Learning"
chapter: true
weight: 3

---

![vFunction Logo](/images/vFunction.png)

### Simulating scheduled learning with the modified OMS app

1. Go to the vFunction Web UI and open the Observation page

2. Add a new schedule for learning

3. Set the controller to *oms-controller*

4. Set the Repeat and the Analysis schedule to daily

5. Set the time slot to 5 min. before the current server time and 10 min. length (e.g., if the current server time is 2:00 PM, set it to 1:55 PM - 2:05 PM)

6. Switch to the terminal of the Linux and run the script in a loop:

```bash
cd ~/oms-tutorial/oms-webmvc/script
for i in `seq 1000`; do ./use-apis.sh ; sleep 0.5; done
```

7. In the vFunction server web ui you should see the schedule learning is active - a rotating arrow next to the schedule name under the schedules section (bottom right). Wait for the learning to complete.
You can also switch to the Learning page and see the controller state by clicking Select Controllers (under ACTIONS)

8. After the learning is done, it will take a minute or two for the analysis to complete and then you should have a new measurement to Select starting with Scheduled (MEASUREMENT->SELECT MEASUREMENT at the bottom of the analysis page)

![vFunction Logo](/images/vFunction.png)