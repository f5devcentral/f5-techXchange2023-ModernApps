###Cleanup Lab Environment

## Trigger destroy of lab environment

1. Open a terminal and run the following commands:
    ```bash
    cd ~/terraform-modular-demo-framework
    terragrunt run-all destroy --terragrunt-modules-that-include ./appstack-lab.hcl
    ```

The output looks as follows:

![](./images/tgrd-appstack-lab.png)

Carefully observe the groups and sequences in which the modules will be applied to destroy the environment. Terragrunt provides this flexibility to perform a full destruction using a single command.

# Lab Complete

> ***Note:*** For a *Ridiculously easy* method to reproduce this demo within UDF, use the steps below 

* Step 1 - Environmental Setup
  ```bash
  terragrunt run-all apply --terragrunt-modules-that-include ./env-setup.hcl
  ```
* Step 2 - Deploy Everything!
  ```bash
   terragrunt run-all apply --terragrunt-modules-that-include ./appstack-lab.hcl
  ```