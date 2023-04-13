## Access the environment
- pick the person on your team who will run the deployment
### Start the UDF blueprint
- find the blueprint
- create a deployment
- start the deployment
- share with teammates, using the share button (f5 email addresses only)
### Log into the DevBox
- decide who uses which box
- RDP into your box
### Observations
 - start VS Code
 - Terragrunt
 - Terraform
 - AZ CLI
 - AWS CLI
 - SOPS

## Prepare the environment for the build

### Gather the required values
- AWS ephemeral credentials
- XC tenant
- XC Volterra Token
- XC P12 File and Password
- XC namespace

### Configure input variables
- open `ef.input.demo.yaml`
- more stuff
### Configure environment variables
- open `ef.env.demo.yaml`
- more stuff

### Observations
- `terragrunt run-all apply` but reply `n` to the prompt to proceed.
- what else?
