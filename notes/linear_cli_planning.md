## What do I want

- To view, add, and edit issues in a command line interface
- View issues for a particular project
- Switch teams with git branch like behavior
- Workspace switching would be a plus, but I don't know if it's possible

## Command List

I want the commands to feel very similar to working with Git via the command line, so that there is a feeling of cohesiveness across the developer experience.

- create
	- issue
	- project
- switch
	- project
	- team
- ls
	- issues
	- projects
	- teams

## Feature list

- Issues
  - Attributes
    - Name
    - Description
    - Sub-issues
    - Status
    - Priority
    - Assignment
    - Estimate
    - Label
    - Project
  - Creation
  - Editing
  - Viewing
  - Methods
    - Take input for name, description, and sub-issues
    - Choose from fields for status, priority, assignment, estimate, label, and
      project

## Stack/Framwork

- Go
  - Cobra
  - Viper
- Linear GraphQL API
