`git` can simply be considered a distrubuted version control system.
It basically keeps track of files on your computer but potentially remote servers as well (like gitlab,github,etc.).

## How it works
```mermaid
flowchart TB
	add(Live) -- git add --> stage(Staged)
	stage -- git commit --> commit(Committed)
	stage -- git restore --staged --> add
	commit -- git reset --soft --> stage
	commit -- git push --> push(Pushed)
	
```


### Adding changes ([man page](https://git-scm.com/docs/git-add))
```bash
git add file_name dir_name
```

### Committing ([man page](https://git-scm.com/docs/git-commit))
```bash
git commit -m "commit message"
```
> Be verbose about what changes happened since your last commit. Your future self will thank you.

### Pushing changes to remote ([man page](https://git-scm.com/docs/git-push))
```bash
git push remote_name branch_name
```
> `remote_name` is `origin` by default.
> To simply call `git push`, set up the default remote once by running `git push -u remote_name branch_name`

### Remove a file from staging ([man page](https://git-scm.com/docs/git-restore))
```bash
git restore --staged file_name
```

### Restore file to last committed version (undo current modifications) ([man page](https://git-scm.com/docs/git-restore))
```bash
git restore file_name
```

### Undo a commit ⚠️ ([man page](https://git-scm.com/docs/git-reset))
```bash
git reset --soft HEAD^
```
This will undo the last commit and put the changes back in staging.
> Be careful with this command. If you pushed the commit to the remote already, you will have to force a push as commit hashes will be different.

## Must know commands
### Status of changes ([man page](https://git-scm.com/docs/git-status))
```bash
git status
```
> Use this all the time to know what changed in your tree.

### Show previous commits ([man page](https://git-scm.com/docs/git-log))
```bash
git log
```
> `git log --oneline --decorate --graph` to get a nice readable log

### Switch braches ([man page](https://git-scm.com/docs/git-branch))
```bash
git branch dev
```
> `git branch -b new_branch` will create `new_branch` and switch to it.

## Example Scenario

```bash
edit file_name
git status
mkdir awesome_dir
edit awesome_dir/awesome_idea
git status
git add file_name awesome_dir
git status
git commit -m "adds awesome idea and edits file_name"
git push
```

## More on git
- [Official website](https://git-scm.com/)
- Branching strategies:
	- [Gitlab Flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html)
	- [Github Flow](https://docs.github.com/en/get-started/quickstart/github-flow)
	- [Microsoft Branching Guidance](https://docs.microsoft.com/en-us/azure/devops/repos/git/git-branching-guidance?view=azure-devops)
	- [Git Flow](https://nvie.com/posts/a-successful-git-branching-model/)
	- [Comparison of Strategies](https://www.gitkraken.com/learn/git/best-practices/git-branch-strategy)
- [A Note About Git Commit Message](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)

