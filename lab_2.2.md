### Virtual K8s and Apps on vk8s

- This lab will be performed by AppDev

### In this Lab
- Create a virtual site identifying XC regional edge locations
- Create a vk8s cluster object in XC, pointing to this virtual site
- Deploy an a container on the vk8s cluster
- Create a Load Balancer pointing to the virtual site pods

### Lab Steps
  - terragrunt run-all apply --terragrunt-modules-that-include ./vk8s-apps.hcl

### Observe
  - Review vk8s configuration and dashboard
  - Review app pods in various sites/REs 
  - Review LB Origin Pool config (virtual site, k8s service name format, etc)
  - Review XC WAAP policy auto-assigned to the LB (created by SecOps)
  - Generate some traffic to your pod and review traffic statistics

### Takeaways
