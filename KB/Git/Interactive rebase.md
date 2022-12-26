Before rebasing the commits, we can modify them! We can do so with an _interactive rebase_. An interactive rebase can also be useful on the branch you're currently working on, and want to modify some commits.

There are 6 actions we can perform on the commits we're rebasing:

-   `reword`: Change the commit message
-   `edit`: Amend this commit
-   `squash`: Meld commit into the previous commit
-   `fixup`: Meld commit into the previous commit, without keeping the commit's log message
-   `exec`: Run a command on each commit we want to rebase
-   `drop`: Remove the commit

Awesome! This way, we can have full control over our commits. If we want to remove a commit, we can just `drop` it.
<iframe border=0 frameborder=0 height=600 width=860 src="https://res.cloudinary.com/practicaldev/image/fetch/s--P6jr7igd--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/msofpv7k6rcmpaaefscm.gif"></iframe>
