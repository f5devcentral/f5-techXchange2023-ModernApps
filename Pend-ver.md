Follow these steps, if you see a *PendingVerification Error* while deploying the environment

1. Destroy the `aws-appstack-site` 

    ```bash
    cd aws-appstack-site-1
    terragrunt destroy
    ```
> **Note:** When prompted to apply, type `yes` then enter.

1. Ensure your site has been removed by checking the *Multi-Cloud Network Connect --> Site Management --> AWS VPC Sites* to ensure there are no sites with your XC username.

1. Run the deployment again

    ```.bash
    cd ~/terraform-modular-demo-framework
    terragrunt run-all apply --terragrunt-modules-that-include ./appstack.hcl
    ```
   