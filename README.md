# LidlFysh-IaC

Example Repo structure for module repository, split by language (Bicep, Terraform - would add Cloudformation and anything else required as needed in same structure).

## Modules
The code container in the Modules folder hierarchy would be deployed using parameter file inputs to provide values, unless there was a specific value we required hardcoded. 

### Resource Modules 
These are individual resources plus any child /extension resources they might require but not related 'parent' resources. E.G. a VM Module would have a disk, NIC and potentially a Public IP but would NOT include Vnet, Subnet, Nat Gateway etc

### Pattern Modules 
These are common patterns / solutions that are used and would commonly reference Resource Modules. For example this could  have references to a Vm Module (with disk, NIC,PIP) and a Network Module (with Vnet, Subnet, Route Table, NACLs , DNS settings) to put together a 'solution' . This would still be deployed using parameters and maintain the approach of being reusable.

## Projects
This would contain more specific code pertaining to specfic scenarios. Potentially this could include configuration / parameters files but also things in development / test that had not yet been approved to be published as modules.

### Customers
For example configuration files for a customer for deploying a pattern module

### LidlFysh 
Used for projects that might be deployed across many customers tenants and that Littlefish would be deciding on settings, changes etc. For example, a solution for deploying a default set of Azure Tags or Monitoring Alerts in all tenants that we manage.

### Test - Development
Used for testing new solutions

## Docs
This folder contains static web site code based on the HUGO and the geekdocs theme, which can be used to automatically publish markdown docs to a static site on Github Pages
This can be seen at [https://philrice.github.io/LidlFysh-IaC/](https://philrice.github.io/LidlFysh-IaC/)
Any time a change or committ is made in the /docs folder a github action runs to deploy this site

