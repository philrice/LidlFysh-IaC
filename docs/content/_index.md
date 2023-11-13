---
title: LidlFysh IaC Documentation Portal
geekdocNav: true
# geekdocAlign: center
geekdocAnchor: true
---

{{< hint type=important >}}

**This is a test and development site!** 

{{< /hint >}}

{{< columns size=large >}}

# LidlFysh-IaC

This is a test site for exploring the concept of creating automated documentation as part of a IaC library of modules and deployments

Example Repo structure for module repository, split by language (Bicep, Terraform - would add Cloudformation and anything else required as needed in same structure).

## Modules
The code contained within the Modules folder hierarchy should aim to be as parametrised as possible to support reuse. Unless there was a specific value we required hardcoded, hardcoded values should be avoided as much as possible and with any restrictions applied using valuer input constraints. Deployments would reference these modules and provide required values as parameter files.

### Resource Modules 
These are individual resources plus any child /extension resources they might require but not including related 'parent' resources. E.G. a VM Module would have a disk, NIC and potentially a Public IP but would NOT include Vnet, Subnet, Nat Gateway etc. Think what would be needed to be configured when you deploy a resource via the admin portal for it to pass validation and what options would usually be chosen / configuration when creating that resource.

### Pattern Modules 
These are common patterns / solutions that are used and would commonly reference Resource Modules. For example this could  have references to a VM Module (with disk, NIC,PIP) and a Network Module (with Vnet, Subnet, Route Table, NACLs , DNS settings) to put together a 'solution' . This would still be deployed using parameters and maintain the approach of being reusable.
Other more complex examples would be Azure Virtual Desktop deployments or entire Azure Landing Zone deployments.

## Projects
This would contain more specific code pertaining to specfic scenarios. Potentially this could include configuration / parameters files but also things in development / test that had not yet been approved to be published as modules.

### Customers
For example configuration files for a customer for deploying a pattern module.
Discussion Point - it might potentially be better to store customer data in a seperate repo, or individual repos? This would provide more granular access control

### Littlefish 
Used for projects that might be deployed across many customers tenants and that Littlefish would be deciding on settings, changes etc. For example, a solution for deploying a default set of Azure Tags or Monitoring Alerts in all tenants that we manage.

### Test - Development
Used for testing new solutions

## Docs
This folder contains static web site code based on the HUGO and the geekdocs theme, which can be used to automatically publish markdown docs to a static site on Github Pages
This can be seen at [https://philrice.github.io/LidlFysh-IaC/](https://philrice.github.io/LidlFysh-IaC/)
Any time a change or committ is made in the /docs folder a github action (could also be run from ADO) runs to deploy this site
Using automated documentation solutions, we can add the output markdown into a documentation site and have it automatically created on the fly.




<br>

{{< /columns >}}
