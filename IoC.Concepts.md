## What's IaC?

- Problem with Manual Config
   - Easy to mis-configure a service.
   - It's hard to manage the expected state of config for compliance.
   - it's hard to transfer config to other teams.

- IaC
   - is a blueprint of your infra,
   - allows you easily share, version, or inventory your cloud infra.

## Popular IaC tools

| Declarative                                        | Imperative                                              |
|----------------------------------------------------|---------------------------------------------------------|
| What you see is what you get. Explicit             | You say what you ant, and the rest is filled in. Impict |
| More verbose, but zero chance of mis-configuration | Less verbose, you could end up with misconfiguration    |
| Uses scripting languages eg. JSON, YAML, XML       | Does more than Declarative                              |
|                                                    |                                                         |
| Examples:                                          | Examples:                                               |
| ARM Templates                                      | Aws Cloud Dev Kit                                       |
| Azure Blue Prints                                  | Pulumi                                                  |
| CloudFormation                                     |                                                         |
| Cloud Deployment Manager                           |                                                         |
| Terraform                                          |                                                         |

## Declarative+
-  Terraform is declarative but tf language features are imperative-like functionality

| Declarative                | Imperative                     | Declarative+             |
| -------------------------- | ------------------------------ | ------------------------ |
| YAML, JSON, XML            | Ruby, Python, JS               | HCL-ish (TF Language)    |
| Limited or no support for  | Imperative features is         | Supports:                |
| imperative-like features   | the utility of the entire      | - Loops (For Each)       |
|                            | feature set of the programming | - Dynamic Blocks         |
| In some cases you can add  | language.                      | - Locals                 |
| behaviour by extending the |                                | - Complex Data Structure |
| base language.             |                                | - Maps, Collections      | 
| E.g CloudFormation Macros  |                                |                          |

## Infrastructure Lifecycle

- What is infra lifecycle?
   - A number of clearly defined and distinct work phases which are used by 
   DevOps Engineers to plan, design, build, test, deliver, maintain and retire cloud infra.

- What is Day 0, Day 1 and Day 2?
   - Day 0-2 is a simplified way to describe phases of an infra lifecycle
   - Day 0: Plan and Design
   - Day 1: Develop and Iterate
   - Day 2: Go live and maintain

 - How does IaC enhance the infra lifecycle?
   - IaC makes changes idempotent, consistent, repeatable, predictable.

Idempotent: No matter how many times you run IaC, you will always end up with the same state that is expected

- Manageability
   - enable mutation via code
   - revised, with minimal changes
  
- Sensibility
   - avoid financial and reputational losses

## Non-Idempotent  vs Idempoten

- Non-Idempotent
When I deploy my IaC config file it will provision and launch 2 vm
When I update my IaC and deploy again, I will end up 2 new VMs with a total of 4 VMs

- Idepotent
When I deploy my IaC config file it will provision and launch 2 VMs
When I update my IaC and deploy again, it will update the VMs if changed by modifying or deleting and creating new VMs

## Provisioning vs Deployment vs Orchestration

- Provisioning 
To prepare a server with systems, data and software, and make it ready for network operations. Example: Puppet, Ansible, Chef, Bash scripts, PowerShell or Cloud-Init.

- Deployment
is the act of delivering a version of your application to run provisioned server. Could be performed with AWS CodePipline, Harness, Jenkis, Github Actions, CircleCI

- Orchestration
is the act of coordinating multiple systems or services. This is a common term when working with microservices, Containers and Kubernetes.

## Configuration Drift

- Is when provisioned infra has an unexpected configuration change due to:
	- team members manually adjusting configuration options
	- malicios actors
	- side affects from APIs, SDK or CLIs.

- Example: A jr. dev turns on Delete on Termination for the production database.
- Config drif going unnoticed could be loss or breach of cloud services and residing data or result in interruption of services or unexpected downtime.

- How to detect config drif?
	- A compliance tool that can detect misconfig. Example: AWS Config, Azure Policies, GCP Security Health Analytics
	- Built-in supprt for drift detection. Example: AWS CloudFormation Drift Decection
	- Storing the expected state. Example: Terraform state files

- How to prevent configuration drift?
	- Immutable infra, always create and destroy, never reuse, Blue, Green deployment strategy.
		- Servers are never modified after they are deployed:
			- Baking AMI images or containers via AWS Image Builder or HashiCorp Packer, or build server. Example: GCP Cloud Run

## Mutable vs Immutable Infra

