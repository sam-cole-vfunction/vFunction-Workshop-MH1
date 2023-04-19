---
title: "Cleanup"
chapter: true
weight: 60

---
![vFunction Logo](/images/vFunction.png)

# Cleanup

In this section, we will clean up the resources created for this workshop by vfunction-workshop package.

1. Log-in to the Workshop Linux VM (using PuTTY in the Workshop Windows VM) and do the following command:

    ```bash
    kubectl delete namespace ingress-nginx
    ```

2. Log in to your AWS Account and open the AWS CloudShell (icon is on top right toolbar)

3. Run the "destroy" script to delete all the resources

    ```bash
    bash ~/vfunction-workshop/destroy.sh
    ```

    Wait for the script to complete

4. Delete the vfunction-workshop-aws-installation.tgz and the vfunction-workshop-aws-installation directory (under your home directory in the cloud shell)

    ```bash
    cd ~
    rm -rf ./vfunction-workshop
    rm vfunction-workshop-aws-installation.tgz
    ```

![vFunction Logo](/images/vFunction.png)
