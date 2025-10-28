# GIT CHEATSHEET

## BASIC

### Rename file

```Bash
git mv ten-cu.txt ten-moi.txt
```

***

## GIT BRANCH MANAGEMENT

#### Check current branch
```bash
git branch
```

#### Create a new branch
```bash
git branch new-branch
```

#### Switch to another branch
```bash
git checkout new-branch
```

#### Create and switch to a new branch
```bash
git checkout -b new-branch
```

#### Rename current branch
```bash
git branch -m new-name
```

#### Rename a specific branch
```bash
git branch -m old-name new-name
```

#### Delete a local branch
```bash
git branch -d branch-name
```
- Deletes `branch-name` if it has been merged

```bash
git branch -D branch-name
```
- Force deletes `branch-name` even if not merged

#### Delete a remote branch
```bash
git push origin --delete branch-name
```

#### List remote branches
```bash
git branch -r
```

#### Push a branch to remote
```bash
git push origin branch-name
```

#### Track a remote branch
```bash
git checkout --track origin/branch-name
```

#### Merge another branch into current
```bash
git merge branch-name
```

***

## COMMIT PROCESS

1. update
```Bash
git update
```
```Bash
git update-git-for-windows
```
2. add file
```Bash
git add .
```
3. commit
```Bash
git commit --m "message"
```
4. push
```Bash
git push
```

***

## GIT CLONE

#### Clone a repository (HTTPS)
```bash
git clone https://github.com/username/repo-name.git
```

#### Clone a repository (SSH)
```bash
git clone git@github.com:username/repo-name.git
```

#### Clone into a specific folder
```bash
git clone https://github.com/username/repo-name.git my-folder
```

#### Clone only a specific branch
```bash
git clone -b branch-name https://github.com/username/repo-name.git
```

#### Clone with shallow history (latest commit only)
```bash
git clone --depth 1 https://github.com/username/repo-name.git
```
- Clones the repo with minimal history (faster & smaller)

#### Clone a subdirectory (sparse checkout)
```bash
git clone --filter=blob:none --no-checkout https://github.com/username/repo-name.git
cd repo-name
git sparse-checkout init --cone
git sparse-checkout set path/to/subdirectory
```
- Clones only a specific folder from the repository (Git 2.25+)

#### Clone a bare repository
```bash
git clone --bare https://github.com/username/repo-name.git
```
- Clones without working directory — used for mirrors or server-side

#### Clone a mirror of the repository
```bash
git clone --mirror https://github.com/username/repo-name.git
```
- Clones all refs and branches — ideal for backups

#### Clone with submodules
```bash
git clone --recurse-submodules https://github.com/username/repo-name.git
```
- Clones the repo and its submodules
