## Access the environment
- pick the person on your team who will run the deployment
### Start the UDF blueprint (NetOps) 
- find the blueprint
- create a deployment
- start the deployment
- share with teammates, using the share button (f5 email addresses only)
### Log into the DevBox (All Personas)
- decide who uses which box
- RDP into your box
### Observations (All Personas)
 - start VS Code
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
- sops `ef.env.demo.yaml`
- check VOLT_API_URL value (check by manually logging in)
- For AWS_ACCESS_KEY_ID, capture from UDF and paste (careful not to include whitespaces/special chars)
- For AWS_SECRET_ACCESS_KEY, capture from UDF and paste (careful not to include whitespaces/special chars)

### Create SSH key for AWS and XC Cloud Cred for AWS deployments
- Programmaticaly create SSH key and import to AWS regions (us-east-2 and us-west-2)
- Programmatically create cloud cred using aws ephemeral creds obtained earlier

### Configure input variables 
- run sops ef.input.demo.yaml
- Modify following variables:
  - project_prefix (use <team>-<number> eg: project_prefix: team-2)
  - resource_owner (use <team>-<number> eg: resource_owner: team-2)
  - useremail (use platform ops persona email)
  - namespace (use <team>-<number> eg: namespace: team-2
  - volterra_cloud_cred_aws: <cloud-cred you created before)
  - domain_name: (use <team>-<number>.sales-demo.f5demos.com eg: team-2.sales-demo.f5demos.com)
 
### Observations
- `terragrunt run-all apply` but reply `n` to the prompt to proceed.
- Review ef.input.demo.yaml values
 
### Notable observations:
  - XC namespace points to team name
  - Azure creds have been created and specific in the file (you created AWS creds above)
  - XC API token and Credential cert (p12) are generated ahead of time and staged in this env for you 
  - AzureSPN client ID and password are generated ahead of time and staged in this env for you 
 
 ### Create AWS and Azure Base environments (NetOps)
  - terragrunt run-all apply --terragrunt-modules-that-include ./base.hcl
 
 ### Observe
  - Log into AWS console (using console link and creds from UDF deployment under "Cloud Accounts")
  - Search for EC2 --> EC2 Global View --> Global Search 
  - type in your project_prefix to identify all the objects created with that project_prefix
 
  - Log into Azure Console (custom credentials)
  - Search for your project_prefix to identify all the objects created with that project_prefix
