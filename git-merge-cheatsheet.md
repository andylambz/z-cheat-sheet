
# Git Merge Cheat Sheet

#### Merge a branch into the current branch
```bash
git merge branch-name
```
- Combines changes from `branch-name` into the current branch
- Creates a merge commit if there are changes
- Requires resolving conflicts if they exist

#### Merge without fast-forward
```bash
git merge --no-ff branch-name
```
- Forces a merge commit even if fast-forward is possible
- Useful for preserving branch history

#### Abort a merge in progress
```bash
git merge --abort
```
- Cancels the merge process
- Only works if a conflict has occurred and merge is incomplete

#### Resolve merge conflicts manually
```bash
# Edit conflicting files
git add conflicted-file.txt
git commit
```
- Open files and fix conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
- Stage the resolved files with `git add`
- Complete the merge with `git commit`

#### View merge conflicts
```bash
git status
```
- Shows which files have conflicts
- Helps track merge progress

#### Merge a remote branch
```bash
git fetch origin
git merge origin/branch-name
```
- Fetches latest changes from remote
- Merges `origin/branch-name` into current branch

#### Merge with squash (combine commits)
```bash
git merge --squash branch-name
git commit
```
- Combines all commits from `branch-name` into one
- Does not record merge history

#### Merge strategy options
```bash
git merge -s recursive -X theirs branch-name
```
- Uses the "recursive" strategy with "theirs" option
- Automatically favors incoming changes during conflict


#### Check merge history
```bash
git log --merges
```
- Shows only merge commits in history
