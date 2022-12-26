Having multiple branches is extremely convenient to keep new changes separated from each other, and to make sure you don't accidentally push unapproved or broken changes to production. Once the changes have been approved, we want to get these changes in our production branch!

One way to get the changes from one branch to another is by performing a `git merge`! There are two types of merges Git can perform: a **fast-forward**, or a **no-fast-forward** 🐢

This may not make a lot of sense right now, so let's look at the differences!

## Fast-forward (`--ff`)

A **fast-forward merge** can happen when the current branch has no extra commits compared to the branch we’re merging. Git is... _lazy_ and will first try to perform the easiest option: the fast-forward! This type of merge doesn’t create a new commit, but rather merges the commit(s) on the branch we’re merging right in the current branch 🥳
<iframe border=0 frameborder=0 height=540 width=860 src="https://res.cloudinary.com/practicaldev/image/fetch/s--cT4TSe48--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/894znjv4oo9agqiz4dql.gif"></iframe>
Perfect! We now have all the changes that were made on the `dev` branch available on the `master` branch. So, what's the **no-fast-forward** all about?

## No-fast-foward (`--no-ff`)

It's great if your current branch doesn't have any extra commits compared to the branch that you want to merge, but unfortunately that's rarely the case! If we committed changes on the current branch that the branch we want to merge doesn't have, git will perform a _no-fast-forward_ merge.

With a no-fast-forward merge, Git creates a new _merging commit_ on the active branch. The commit's parent commits point to both the active branch and the branch that we want to merge!
<iframe border=0 frameborder=0 height=540 width=860 src="https://res.cloudinary.com/practicaldev/image/fetch/s--zRZ0x2Vc--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/rf1o2b6eduboqwkigg3w.gif"></iframe>

No big deal, a perfect merge! 🎉 The `master` branch now contains all the changes that we've made on the `dev` branch.