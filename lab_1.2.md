# Deploy App and Sitemesh

This lab will be deployed by AppDev

In this Lab you will:

- Deploy 2 VMs one in AWS and one in Azure in spoke VPC/VNET
- You will also provision the AWS VM with the F5 Demo app
- Construct a load balancer on XC using Private IP origin
- Construct a site mesh group between the AWS and Azure XC Sites

## Lab Steps

1. Run the following command:

  ```bash
  terragrunt run-all apply --terragrunt-modules-that-include ./vm-app-mesh.hcl
  ```

## Observe

- XC WAAP policy auto-assigned to LB (created by Sec Ops in previous step)
- Traverse from VM in Azure to the App in AWS
  - From the Azure VM, open XC Load Balanced FQDN (advertised to internet)
  - From the Azure VM, curl to the private IP in AWS (advertised to Site mesh)

## Takeaways

TODO: TBD
