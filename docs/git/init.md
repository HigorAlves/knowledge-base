# Simple commit conventions for internet citizens.

When you commit, you are contributing to a community or project, so we should treat commits as a great asset!

It provides an easy set of rules for creating an explicit commit history; which makes it easier to write automated tools on top of. This convention dovetails with SemVer, by describing the features, fixes, and breaking changes made in commit messages.

So let's be clear!

The commit message should be structured as follows:

```
<type>(scope): <description>
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

---

# More Topics

- [Signing commits]() **WIP**
- [Git Flow]() **WIP**
