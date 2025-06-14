## quick note

Attributes like priority, assignment, etc. (those with predefined selection options) in the struct will point to those options within the API when they are called.

fzf search integration for finding issues?

pass in api key to get request so that linear hears me yelling at it

- get server sends api key to api and receives auth info
- post server sends queries to api and processes user requests
- get server (second one?) receives the changes and lists them out(?)

### GET

- teams
- users
- status options
- priority options
- assignee options (same as users)
- label options
- estimate options
- projects

status, priority, and estimate are all options with predefined values
that I can pick between (with code action like key input?)

projects and teams are variables, as I can add new ones whenever
