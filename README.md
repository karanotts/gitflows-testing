This repository uses **[semantic-release](https://semantic-release.gitbook.io/semantic-release/)** to automate versioning, changelog updates, and GitHub releases.

#### How it works
- Every push to `main` is analyzed for **Conventional Commit** messages.  
- semantic-release bumps the version, updates the changelog, and creates a GitHub Release automatically.  
- JIRA ticket references in commit messages are preserved in changelogs for traceability.

#### Commit message format
Each commit should include both a **conventional prefix** and the **JIRA issue key**.  
A few valid examples:

| Commit message | Meaning | Result |
|-----------------|----------|---------|
| `feat(IN-1234): add user role management` | New feature | Minor release |
| `fix(DI-2233): handle null values in report` | Bug fix | Patch release |
| `feat!(IN-7777): remove legacy endpoint` | Breaking change | Major release |

You can also use `BREAKING CHANGE:` in the body if needed.

#### Branch naming
Feature and bugfix branches usually follow:
`feature/IN-1234`
`bugfix/DI-2233`

When merging into `main`, make sure at least one commit or the squash message follows the conventional pattern above.

#### Quick guide
1. Write commits in the format shown.  
2. Merge (or push) to `main`.  
3. GitHub Actions runs the release workflow — version tag, changelog, and GitHub Release are all created automatically.