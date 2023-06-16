Everyone makes mistakes, and that's totally okay! Sometimes it may feel like you've screwed up your git repo so badly that you just want to delete it entirely.

`git reflog` is a very useful command in order to show a log of all the actions that have been taken! This includes merges, resets, reverts: basically any alteration to your branch.
<iframe border=0 frameborder=0 height=520 width=860 src="https://res.cloudinary.com/practicaldev/image/fetch/s--MMUdOS0P--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/1aqek1py1knwl926ele7.gif"></iframe>
If you made a mistake, you can easily redo this by resetting `HEAD` based on the information that `reflog` gives us!

Say that we actually didn't want to merge the origin branch. When we execute the `git reflog` command, we see that the state of the repo before the merge is at `HEAD@{1}`. Let's perform a `git reset` to point HEAD back to where it was on `HEAD@{1}`!
<iframe border=0 frameborder=0 height=520 width=860 src="https://res.cloudinary.com/practicaldev/image/fetch/s--A1UMM2AH--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/9z9rhtbw7mrigp0miijz.gif"></iframe>
We can see that the latest action has been pushed to the `reflog`!