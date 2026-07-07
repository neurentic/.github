# Contribution guide

This guide defines the working standards for this repository with the goal of maintaining consistency, quality, and traceability.

## ♻️ General workflow

1. Create an issue describing the task or bug, when applicable. 
2. Switch to `develop` and update the local branch: 

```bash 
git checkout develop git pull origin develop 
``` 

3. Create a working branch from `develop`: 

```bash 
git checkout -b feature/short-description 
``` 

4. Make the changes with small, descriptive commits. 
5. Push the working branch to the remote repository: 

```
bash git push -u origin feature/short-description 
``` 

6. Create a Pull Request into `develop`, linking the corresponding issue when one exists. 
7. Wait for the Pull Request to be reviewed and approved. 
8. Merge the Pull Request using **Squash merge**. 
9. Delete the working branch after merging it. 

Branches `feature/*`, `fix/*`, `chore/*`, `docs/*`, and `refactor/*` must always merge into `develop`. 
When publishing a stable version, create a Pull Request from `develop` to `main`. 

```text 
feature/*  ──┐ 
fix/*      ──┤ 
chore/*    ──┼──> develop ──> main 
docs/*     ──┤
refactor/* ──┘ 
``` 

### Important rules 

- `main` represents the stable production code. 
- `develop` is the default working and integration branch.
- `main` must be protected. 
- Never push directly to `main`. 
- `main` can only receive changes from `develop` through a Pull Request. 
- All work must start from an up-to-date `develop`. 
- Working branches must be created from `develop`. 
- Working branches must be merged back into `develop`. 
- Pull Requests must be reviewed and approved before merging. 
- **Squash merge** must be used when closing a Pull Request. 
- Branches that have already been merged must be deleted. 

If you are on `main`, switch to `develop` before starting work: 

```bash 
git checkout develop 
git pull origin develop 
```

## 🪾 Branch naming convention

Formato:

```text
type/short-description
```

| Type        | Use                                                | Example                        |
| ----------- | -------------------------------------------------- | ------------------------------ |
| `feature/`  | New features                                       | `feature/user-authentication`  |
| `fix/`      | Bug fixes                                          | `fix/login-validation-error`   |
| `refactor/` | Improvements without functional changes            | `refactor/reorganize-services` |
| `chore/`    | Technical tasks, such as dependencies or config    | `chore/update-dependencies`    |
| `docs/`     | Documentation                                      | `docs/improve-docs`            |

## ⬆️ Commit convention

We use **Conventional Commits**.

* Use the imperative mood: `add`, not `added`.
* The title should be approximately 50 characters max.
* Do not add a period at the end.

### Structure

```text
type: short description
```

### Allowed types

* `feat`: New feature.
* `fix`: Bug fix.
* `docs`: Documentation.
* `style`: Formatting changes, such as spaces or commas.
* `refactor`: Refactoring without behavior changes.
* `test`: Tests.
* `chore`: Miscellaneous maintenance tasks.

### Example

```text
feat: add script to move leg
```

## 🧹 Maintenance

* Update dependencies periodically.
* Delete obsolete branches after merging them.
* Keep the `README.md` file up to date.
