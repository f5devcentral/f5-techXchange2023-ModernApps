# Kubeconfig and Managed K8s

You will now obtain a kubeconfig from the Managed K8s site 

## Trigger build of lab environment

1. Open a terminal and run the following command to switch to the infrastructure branch we will use for this lab:

    ```bash
    cd ~/terraform-modular-demo-framework
    terragrunt run-all apply --terragrunt-modules-that-include ./kubeconfig.hcl
    ```

2. Deploy Virtual Site and Virtual K8s resources
3. Deploy Brewz app on Mk8s and Vk8s
4. Create XC Load Balancer with custom routes

## Next Step  [ ](lab_1.1.md)