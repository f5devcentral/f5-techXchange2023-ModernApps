### Deploy App and Sitemesh

This lab will be deployed by DevOps

In this Lab you will 
  - deploy 2 VMs one in AWS and one in Azure in spoke VPC/VNET
  - You will also provision the AWS VM with the F5 Demo app
  - Construct a load balancer on XC using Private IP origin
  - Construct a site mesh group between the AWS and Azure XC Sites

### Lab Steps
  - terragrunt run-all apply --terragrunt-modules-that-include ./vm-app-mesh.hcl

### Observe
  Traverse from VM in Azure to the App in AWS
    - from the Azure VM, open XC Load Balanced FQDN (Advertized to internet)
    - from the Azure VM, curl to the private IP in AWS (Advertized to Site mesh)

### Takeaways 
