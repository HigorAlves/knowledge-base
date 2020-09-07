# Simple commit conventions for internet citizens.

When you Git, you are contributing to a community or project, so we should treat Git as a great asset!

## Repository

## Configuration file

The configuration file used by Git is `~/.gitconfig`. Here is an example:

```
[user]
  name = <YOUR-NAME>
  email = <YOUR-EMAIL>
[core]
  editor = vim
  whitespace = fix,-indent-with-non-tab,trailing-space,cr-at-eol
  excludesfile = ~/.gitignore
[push]
  default = matching
[pull]
  rebase = preserve
[branch]
  autosetuprebase = always
[color]
  ui = auto
[color "branch"]
  current = yellow bold
  local = green bold
  remote = cyan bold
[color "diff"]
  meta = yellow bold
  frag = magenta bold
  old = red bold
  new = green bold
  whitespace = red reverse
[color "status"]
  added = green bold
  changed = yellow bold
  untracked = red bold
[diff]
  tool = vimdiff
  compactionHeuristic = true
[difftool]
  prompt = false
[alias]
  a = add --all
  ai = add -i
  bd = branch -d
  ci = commit
  ca = commit -a
  cm = commit -m
  cam = commit -a -m
  cim = commit --amend
  l = log --oneline
  lg = log --oneline --graph --decorate
  me = merge
  co = checkout
  cob = checkout -b
  ps = push
  st = status
  tree = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
```

## Workflow

### Commit Messages
It provides an easy set of rules for creating an explicit commit history; which makes it easier to write automated tools on top of. This convention dovetails with SemVer, by describing the features, fixes, and breaking changes made in commit messages.

The commit message should be structured as follows:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

The commit contains the following structural elements, to communicate intent to the consumers of your library:


- `fix`: This type patches a bug in your codebase (this correlates with PATCH in semantic versioning).
- `feat`: This type introduces a new feature to the codebase (this correlates with MINOR in semantic versioning).
- `ci`: Changes to CI configuration files and scripts
- `docs`: Documentation only changes
- `perf`: A code change that improves performance
- `refactor`: A code change that neither fixes a bug nor adds a feature
- `style`: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- `test`: Adding missing tests or correcting existing tests

Always use small commits, specific for each separate task you are doing.

Always use rebase to update your feature branches before merging into develop. This helps maintain a clear history and prevents overly complicated merge conflicts. However, be careful to NEVER rebase a branch that is being used by someone other than yourself, that could cause very difficult issues to solve.

### Feature Branches

|Branch|Purpose|Audience|
|:----:|:-----|:------:|
|`feat/*`|New feature|Developers|Developers|
|`fix/*`|A bug fix|Developers|Developers|
|`doc/*`|Documentation only changes|Developers|
|`refactor/*`|A code change that neither fixes a bug or adds a feature|Developers|
|`test/*`|Adding missing tests|Developers|
|`develop`|Continuous integration testing|Developers|
|`staging/x.y.z`|Beta Candidate on Test fase|QA testers|
|`beta/x.y.z`|Release Candidate on Test fase|External/Product testers|
|`release/x.y.0`|Release candidates|External testers|
|`hotfix/x.y.z`|Hotfix release candidates|External testers|
|`main`|Latest public release|Store available|

## Code Reviews

---

# More Topics

- [Signing commits]() **WIP**
- [Git Flow]() **WIP**
