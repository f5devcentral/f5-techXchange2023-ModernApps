### Cleanup Lab Environment

## Lab Teardown

1. In the lab **devbox** VM, open a terminal and run the following script to initiate teardown of the infrastructure built for this lab:

    ```bash
    cd ~/terraform-modular-demo-framework
    ./appstack-lab/teardown-lab-environment.sh 
    ```

    > **Note:** Ensure that the script has completed successfully before disconnecting from the VM. If you see *API Timeout exceeded* errors, please wait 3-5 mins, and re-attempt teardown script. This error is due to rate limiting by the XC API. If you are unable to get a clean destroy, please make the lab instructors aware.

<br/>
<br/>
 Terragrunt provides this flexibility to perform a full destruction, in the reverse sequence of deployment, using a single command.
<br/>
<br/>

2. Shut down and delete the UDF deployment.

## END OF LAB




<br/>
<br/>

# Lab Complete

>  For a *__Ridiculously easy__* method to reproduce this demo within UDF, use the steps below 

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
    cd ~/terraform-modular-demo-framework
    ./appstack-lab/teardown-lab-environment.sh 
```