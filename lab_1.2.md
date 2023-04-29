###Cleanup Lab Environment

## Trigger destroy of lab environment

1. Open a terminal and run the following commands:
```bash
    cd ~/terraform-modular-demo-framework
    terragrunt run-all destroy --terragrunt-modules-that-include ./app-lab.hcl
    terragrunt run-all destroy 
    --terragrunt-modules-that-include ./kubeconfig.hcl
    terragrunt run-all destroy  --terragrunt-modules-that-include ./appstack.hcl
    terragrunt run-all destroy  --terragrunt-modules-that-include ./env-setup.hcl
    ```