The following steps are to be performed by Platform Ops Persona in each team

### Build VPC and VNET sites (Platform Ops)
  - terragrunt run-all apply --terragrunt-modules-that-include ./sites.hcl

### Observe outputs:
  - Log into XC console 
  - Review VPC and VNET Site objects
  - Log into AWS/Azure console
  - Search using "project_prefix" to identify all components built for your team number


### Note
  - The sites take over 30 mins to change to "online" state, this is expected
  - If you see "Applied with Errors" or "Waiting for Registration", please ping the lab instructors
   
