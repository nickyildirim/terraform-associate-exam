## TF Lifecycle

- Steps (Lifecycle)
	- Code: Write or Update your TF configuration file
	- Init: Initialize your project Pull latest providers and modules
	- Plan: Speculate what will change or Generate a saved execution plan
	- Validate: Ensure types and values are valid, ensures required attributes are present
	- Execute: the terraform plan provisioning the infra
	- Destroy: the remote infra

## Change Automation

- A standard approach to apply change, and resolving conflicts brought about by change. In the context of IaC, Change management is the procedure that will be followed when resources are modify and applied via config script.
- What's change automation:
	- a way of automatically creating consistent, systematic, and predictable way of managing change request via controls and policies

Note: TF uses change automation in the form of execution plans and resources graphs to apply and review complex changesets.


## Execution Plans

- An manual review of what add, change or destroy before you apply change. Example: 
  `terraform apply`

## Visualizing Executions Plans

- You can visualize an execution plan as a graph using the terraform graph command. Terraform will output a GraphViz file (you'll need GraphViz installed to view the file)
   `terraform graph | dot -Tsvg > graph.svg`

## TF Resource Graph

- TF builds a dependency graph from the TF configurations, and walks this graph to generate plans, refresh states, and more.
	- When you use `terraform graph`, this is visual presentation of the dependency graph
