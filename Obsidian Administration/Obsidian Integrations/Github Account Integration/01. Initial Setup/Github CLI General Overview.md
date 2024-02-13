#github #github-cli #access-token #git #github-desktop #obsidian #obsidian-integration

>The following text is a brief overview of the command syntax and arguments, as well as flags available for use within the github-cli application...

- [9] General Usage:
---
```github-cli
  gh <command> <subcommand> [flags]
```

- [8] Core Commands:
---
```github-cli
  auth:        Authenticate gh and git with GitHub
  browse:      Open the repository in the browser
  codespace:   Connect to and manage codespaces
  gist:        Manage gists
  issue:       Manage issues
  org:         Manage organizations
  pr:          Manage pull requests
  project:     Work with GitHub Projects.
  release:     Manage releases
  repo:        Manage repositories
```

- [7] Github Action Commands:
---
```github-cli
  cache:       Manage Github Actions caches
  run:         View details about workflow runs
  workflow:    View details about GitHub Actions workflows
```

- [6] Preinstalled Alias Commands:
---
```github-cli
  co:          Alias for "pr checkout"
```

- [5] Additional Commands: 
---
```github-cli
  alias:       Create command shortcuts
  api:         Make an authenticated GitHub API request
  completion:  Generate shell completion scripts
  config:      Manage configuration for gh
  extension:   Manage gh extensions
  gpg-key:     Manage GPG keys
  label:       Manage labels
  ruleset:     View info about repo rulesets
  search:      Search for repositories, issues, and pull requests
  secret:      Manage GitHub secrets
  ssh-key:     Manage SSH keys
  status:      Print information about relevant issues, pull requests, and notifications across repositories
  variable:    Manage GitHub Actions variables
```

- [4] Help Topics: 
---
```github-cli
  actions:     Learn about working with GitHub Actions
  environment: Environment variables that can be used with gh
  exit-codes:  Exit codes used by gh
  formatting:  Formatting options for JSON data exported from gh
  mintty:      Information about using gh with MinTTY
  reference:   A comprehensive reference of all gh commands
```

- [3] Flags: 
---
```github-cli
  --help      Show help for command
  --version   Show gh version
```

- [2] Examples:
---
```github-cli
  $ gh issue create
  $ gh repo clone cli/cli
  $ gh pr checkout 321
```

- [1] Learn More: 
---
```github-cli
  Use `gh <command> <subcommand> --help` for more information about a command.
  Read the manual at https://cli.github.com/manual
  ```


