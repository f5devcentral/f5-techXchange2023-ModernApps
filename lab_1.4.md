### Cleanup Lab Environment

## Trigger destroy of lab environment

1. In a terminal run the following command:
    ```bash
    terragrunt run-all destroy --terragrunt-modules-that-include ./appstack-lab.hcl
    ```


The output looks as follows:
<br/>
<br/>
![](./images/tgrd-appstack-lab.png)
<br/>
<br/>
Carefully observe the groups and sequences in which the modules will be applied to destroy the environment. Terragrunt provides this flexibility to perform a full destruction using a single command.
<br/>
<br/>

> ***Note:*** If you see the errors, they are most likely due to XC API throlling or timeouts. Just re-attempt the previous step, and type 'y' when prompted. If you are unable to get a clean destroy, please make the lab instructors aware.
<br/>
<br/>

# Lab Complete

> ***Note:*** For a *__Ridiculously easy__* method to reproduce this demo within UDF, use the steps below 

<br/>
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
<br/>

* Step 4 - Destroy Everything! 
   ```bash
   terragrunt run-all destroy --terragrunt-modules-that-include ./appstack-lab.hcl
   terragrunt run-all destroy --terragrunt-modules-that-include ./env-setup.hcl
  ```