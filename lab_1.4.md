### Cleanup Lab Environment

## Lab Teardown

1. In the lab **devbox** VM, open a terminal and run the following script to initiate teardown of the infrastructure built for this lab:

1. In a terminal run the following command:

    ```bash
    cd ~/terraform-modular-demo-framework
    ./appstack-lab/teardown-lab-environment.sh 
    ```

Terragrunt will destroy all the deployed modules, in the reverse sequence of deployment (Last-in-first-out)

> ***Note:*** If you see errors, they are likely due to XC API throttling or timeouts. Please re-attempt the previous step, and type 'y' when prompted. If you are unable to get a clean destroy, please make the lab instructors aware. You may have to re-attempt this command 3 to 4 times
<br/>
<br/>

Next, destroy the objects specific to the UDF environment:
<br/>
  ``` bash
  terragrunt run-all destroy --terragrunt-modules-that-include ./env-setup.hcl
  ```


# Lab Complete

## Ridiculously Easy Demos
>  To reproduce this demo within UDF, use the steps below

<br/>

* Step 1 - Environmental Setup

  ```bash
  terragrunt run-all apply --terragrunt-modules-that-include ./env-setup.hcl
  ```

* Step 2 - Deploy Everything!

  ```bash* Step 2 -
   terragrunt run-all apply --terragrunt-modules-that-include ./appstack-lab.hcl
  ```

* Step 3 - Illustrate the various features, settings, locations, etc as needed
<br/>
Suggestions:
1. Virtual K8s cluster/services/deployments/pods
1. Managed K8s clusters/services/deployments/pods
1. Site locations for Mk8s
1. Site locations for Vk8s virtual site
1. Analytics dashboard 
<br/> 
<br/>

* Step 4 - Destroy Everything! 
    ```bash
    terragrunt run-all destroy --terragrunt-modules-that-include ./appstack-lab.hcl
    terragrunt run-all destroy --terragrunt-modules-that-include ./env-setup.hcl 
    ```