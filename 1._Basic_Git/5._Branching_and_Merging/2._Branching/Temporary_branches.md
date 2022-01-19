# Temporary branches
Created Sunday 03 January 2021

Suppose we want to demo an app, with code from a specific commit. Normally we'd create a branch, ``reset`` to the required commit and then build/run our project.

This is a lot of work.

Git allows us to have temporary branches, i.e they exists only until we switch the branch.

Syntax
	git checkout SHA_id # creates a new branch with HEAD at the commit 

