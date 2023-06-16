Another way of undoing changes is by performing a `git revert`. By reverting a certain commit, we create a _new commit_ that contains the reverted changes!

Let's say that `ec5be` added an `index.js` file. Later on, we actually realize we didn't want this change introduced by this commit anymore! Let's revert the `ec5be` commit.
<iframe border=0 frameborder=0 height=520 width=860 src="https://res.cloudinary.com/practicaldev/image/fetch/s--eckmvr2M--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/3kkd2ahn41zixs12xgpf.gif"></iframe>
Commit `9e78i` reverted the changes that were introduced by the `ec5be` commit. Performing a `git revert` is very useful in order to undo a certain commit, without modifying the history of the branch.
