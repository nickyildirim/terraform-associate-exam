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
|----------------------------------------------------|---------------------------------------------------------|
| Examples:                                          | Examples:                                               |
| ARM Templates                                      | Aws Cloud Dev Kit                                       |
| Azure Blue Prints                                  | Pulumi                                                  |
| CloudFormation                                     |                                                         |
| Cloud Deployment Manager                           |                                                         |
| Terraform                                          |                                                         |
|----------------------------------------------------|---------------------------------------------------------|

## Declarative+
-  Terraform is declarative but tf language features are imperative-like functionality

| Declarative                | Imperative                     | Declarative+             |
|----------------------------|--------------------------------|--------------------------|
| YAML, JSON, XML            | Ruby, Python, JS               | HCL-ish (TF Language)    |
|----------------------------+--------------------------------+--------------------------|
| Limited or no support for  | Imperative features is         | Supports:                |
| imperative-like features   | the utility of the entire      | - Loops (For Each)       |
|                            | feature set of the programming | - Dynamic Blocks         |
| In some cases you can add  | language.                      | - Locals                 |
| behaviour by extending the |                                | - Complex Data Structure |
| base language.             |                                | - Maps, Collections      |
| E.g CloudFormation Macros  |                                |                          | 
|----------------------------|--------------------------------|--------------------------|

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
