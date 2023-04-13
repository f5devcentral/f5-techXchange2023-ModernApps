### Managed K8s Cluster Object and Appstack sites

- The steps in this lab will be performed by Platform Ops

- In this lab you will:
  - Build a Managed K8s (mk8s/pk8s) cluster object in XC
  - Build XC Appstack sites in AWS/Azure
  
### Lab Steps
- terragrunt run-all apply --terragrunt-modules-that-include ./mk8s-appstack.hcl

### Observe
- In XC Console - Review the mk8s cluster object under Distributed Apps --> Managed K8s 
- In AWS/Azure Console - Review the nodes created for the Appstack site

### Note
  - This process takes over 20 mins to complete, before sites show "online". This is expected
  - If you see "waiting for registration" or "applied with errors" please contact the lab instructors
