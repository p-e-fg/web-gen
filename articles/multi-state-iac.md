### Multi-State IaC (Work In Progress)

Having your infra described in code is important for many reasons. The next step, the usability / deploy-ability of that code, is equally as important. Many cloud providers lean on multi state vs. single or few state IaC as a best or only practice, for example AWS CloudFormation Stacks or Terraform Cloud Workspaces, as they realize there are pitfalls with large IaC states...

#### There are a number of considerations we should make when it comes to your IaC state:

##### Concurrency
- Typically, IaC systems will have a state locking mechanism, whereby only one change in state can happen at a given time
- More states mean more concurrency and less locking issues

##### Fungability
- When you scope your states, they are easier to destroy; less worry
- Large, multi environment single state files for example are very difficult to destroy, as they contain "too much" and are scary to work with

##### Access
- When you separate states and state files, the accessability of those are clear and can be segregated
- The opposite is that too many actors have access to too big of a state

