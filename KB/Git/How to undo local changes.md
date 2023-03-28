To undo changes made to a file in the source directory:
	`git checkout -- <file>`

To undo a local stage (git add):
	`git restore --staged <file>`
	or
	`git reset <file>`

To undo a local commit:
	find the commit ID:
	`git reflog`
	Revert it:
	`git revert <commit ID>`

To undo everything up to and including a certain local commit:
	find the commit ID:
	`git reflog`
	Hard reset it:
	`git reset --hard <commit ID>`

If you had already pushed your committed changes, it is  recommended not to hard reset a shared branch. Use `git revert <commit id>` instead
