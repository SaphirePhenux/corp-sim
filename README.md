
# Corporate Simulator (corp-sim)

## Summary: 

Corporate Simulator, or corp-sim for short, is an end-to-end environment simulator home/test lab for IT practicioners and students to practice, pretend, and play around with.

## Full Description:

Corporate Simulator, or corp-sim for short, is an end-to-end environment simulator that seeks to provide way for companies, developers, and general IT practictioners a way to see how traffic might travel through the pipes and how it could be affected by other components in the network. In other words, this is a home/test lab to practice, pretend, and play around with.

Corp-Sim is built using Terraform for infrastructure design/creation and Ansible/Puppet to install and configure the required software on all the machines. As of the time of creation/writing (Jan. 2022), Corp-Sim is planned to have 3-4 different Corporate environments to choose from, but the full list is still to be determined. 

The initial version of Corp-Sim, v0.01-Alpha, is currently slated to be cloud agnostic/use multiple cloud providers in order to 
show/teach how to interact with different cloud providers using Terraform. There might be AWS and Azure cli examples as well.

CloudDrift will be used to connect Terraform with the different providers.

The infrastructure will be built using a mix of containers/stateless services and full virtual servers.

## Folder Structure

**NOTE:** The initial folder structure is currently designed around one (1) Corp scenario. Later versions will be broken out into different scenario (sub) folders.
Repo+
    |
    +-src+: contains the source code and data sets for the different programs, services, and databases.
    |    |
    |    +-Data: the seed data 
    |    +-Services: the different services source code
    |
    +-tf/cloud+: the infrastructure as code in Terraform
    |         |
    |         +aws: the AWS Terraform code
    |         +azure: the Azure Terraform code
    |         +gcp: the GCP Terraform code
    |
    +-config: the different configurations for each of the different servers and services
    |
    +-automation+: the ansible and puppet playbooks as well as the ninja templates
    |           |
    |           +ansible: ansible playbooks and jinja templates
    |           +puppet: puppet configs, playbooks, and modules
    | 
    +-scenario: a collection of readme's and other markdown documents that explains the background, servers, and services for each scenario available.
    |
    +-monitoring+: a collection of documents explaining the usage of the different monitoring services





## Current To Do List

- Finish general infrastructure and network design charts.
  This will be done using either figjam, lucidchart, or some other design software.
		- AWS Design Chart
		- Azure Design Chart
  - GCP Design Chart
- Build out the initial folder structure
- Build the initial Terraform
- Build the initial Ansible and Puppet Playbooks
- Build the initial Monitoring Dashboard (Monitors currently active scenarios)
- Write out the documentation for the different scenarios and services  



## Currently Planned Scenarios (Quick Sections Overview)

**NOTE:** Since these are designed to be for general practice with fake data and not actual use, some of these scenarios will not be fully reflective of correct layouts...
      AKA I'm lazy and don't want to spend time dealing with fully PII (Personally identifiable information) practices.
+ Movie Rental/General Retail Store
  - HQ: LDAP/Radius, Finance, HR, Owner, Database, Web servers
  - Store: POS, Manager
  - End User: remote / online customer
+ Financial Processor
  - Online/App users (End Users who use the Frontend API)
  - DMZ/Front: Frontend API services, Public/Customer facing Website
  - Back: Backend API servers, databases
  - Corporate: LDAP, workstations/vdi's, nfs server
