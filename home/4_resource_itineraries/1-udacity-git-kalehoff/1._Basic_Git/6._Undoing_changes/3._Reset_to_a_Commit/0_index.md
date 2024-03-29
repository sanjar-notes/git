# 3. Reset to a Commit
Created Monday 09 November 2020


* Reset means to get rid of some work and start again.
* Resetting is different from reverting. It actually *erases *all successive commits.
* When we reset to a commit, all successive commits are deleted permanently.
* You may lose contents of the *working tree* and *staging area*. Fortunately, Git, by default, doesn't touch these area.

![](/assets/3._Reset_to_a_Commit-image-1.png)

'git reset' Command
-------------------
	git reset SHA_id #SHA_id becomes the starting point

Commits are deleted, but what about the index and worktree. Three scenarios(options) are possible:

* ``--soft`` - No change in worktree and index.
* ``--mixed`` - Only index is reset. This is the **default**.
* ``--hard`` - All areas are cleared. **Most dangerous**. You lose the worktree and index.


MAID - keep in mind that WD is safe except in --hard.
The default option for reset is --mixed. You'll lose the WD.

