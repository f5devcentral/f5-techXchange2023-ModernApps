# This lab requires Platform Ops and Sec Ops to perform specific functions

The following steps are to be performed by Platform Ops Persona in each team

## Build VPC and VNET sites (Platform Ops)

1. Run the following command:

  ```bash
  terragrunt run-all apply --terragrunt-modules-that-include ./sites.hcl
  ```

## Observe

1. Log into XC console

1. Review VPC and VNET Site objects

1. Log into AWS/Azure console

1. Search using "project_prefix" to identify all components built for your team number

  > **Note:** The sites take over 30 mins to change to "online" state, this is expected. If you see "Applied with Errors" or "Waiting for Registration", please ping the lab instructors.

**The following steps are to be performed by Sec Ops Persona in each team:**

### Build a WAAP policy

1. Run the following command:

  ```bash
  terragrunt run-all apply --terragrunt-modules-that-include ./xcwaap.hcl
  ```

### Observe

1. In the XC Console, navigate to **Home --> Web App & API Protection --> \<select your team namespace>**

1. Review the policy object you just created.

### Takeaways

TODO: TBD
