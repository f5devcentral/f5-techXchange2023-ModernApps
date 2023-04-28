# Objectives
This lab introduces you to the strucrture of Terraform Modular Demo Framework, and illustrates deployment of an App on XC Managed K8s and XC Virtual K8s cluster.

## Access the environment

-- Log into https://udf.f5.com 
-- Look for "Terraform Modular Demo Framework" under "Blueprints", then Deploy (use Systems Engineers cost center)
-- Go to "Deployments" --> Find the deployment, and click "Start"


### Log into the DevBox 

- RDP into the devbox
    > ***Note:*** - The devbox has all necessary tools installed, so RDP is the preferred method for completing this lab.

### Observations (All Personas)

- Start VS Code
- Terragrunt
- Terraform
- AZ CLI
- AWS CLI
- SOPS

## Prepare the environment for the build (Platform Ops) (share screen in breakouts as needed)

### Gather the required values

- AWS ephemeral credentials
- XC tenant
- XC Volterra Token
- XC P12 File and Password
- XC namespace

### Configure environment variables

1. Run the following:

```bash
sops `ef.env.demo.yaml`
```

1. Check the `VOLT_API_URL` value (check by manually logging in)

1. For `AWS_ACCESS_KEY_ID`, capture this from UDF and paste (careful not to include whitespaces/special chars)

1. For `AWS_SECRET_ACCESS_KEY`, capture this from UDF and paste (careful not to include whitespaces/special chars)


### Configure input variables

1. look for "terragrunt.hcl" in the root directory of "terraform-modular-demo-framework"
   1. Modify the "teamname" value to match the format below:
      1. <(first-name-initial)>.<(last name)>" (eg: j-smith for John Smith)
   
2. Run `sops ef.input.demo.yaml`

3. Modify the following variables:
    - `project_prefix` (use \<team>-\<number> eg: project_prefix: team-2)
    - `resource_owner` (use \<team>-\<number> eg: resource_owner: team-2)
    - `useremail` (use platform ops persona email)
    - `namespace` (use \<team>-\<number> eg: namespace: team-2
    - `volterra_cloud_cred_aws`: \<cloud-cred you created before)
    - `domain_name`: (use \<team>-\<number>.sales-demo.f5demos.com eg: team-2.sales-demo.f5demos.com)

4. 

### Observations

1. Run the following:

  ```bash
  terragrunt run-all apply --terragrunt-modules-that-include ./env-setup.hcl
  ```

  > **Note:** When prompted, reply `y` to the prompt to proceed.



> *** Note:*** This step triggers a terraform module to create the environment variables and input variables for the rest of the lab. This is specific to the UDF environment only 

### Notable Observations

- XC namespace points to team name
- Azure creds have been created and specific in the file (you created AWS creds above)
- XC API token and Credential cert (p12) are generated ahead of time and staged in this env for you
- AzureSPN client ID and password are generated ahead of time and staged in this env for you

### Create AWS and Azure Base environments (NetOps)

1. Run the following:

  ```bash
  terragrunt run-all apply --terragrunt-modules-that-include ./appstack.hcl
  ```

### Observe

