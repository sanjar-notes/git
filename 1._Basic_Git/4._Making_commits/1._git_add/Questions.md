# Questions
Created Tuesday 10 November 2020

Questions(Optional)
-------------------

17. What's the need of a staging area. Why not just commit the project when we're done making the changes. Isn't** git commit** enough?
18. There are many reasons why a staging area is useful:
	1. **Staging helps you split up one large change into multiple commits** - suppose you worked on many features but did not commit any of them. Now, you're smart and know that unrelated features shouldn't be in a single commit. So you start 'staging and committing' the related files, feature by feature. This way we have different commits for different tasks, just the way it should be.
	2. **Staging helps in reviewing changes before committing** - Suppose we have many small but related tasks which we wish to commit together. So we do one task at a time and stage the respective files as we complete each task. When we are done, we do 'git status -v' to see all files that we've changed, in order. We commit it all.
	3. **Staging helps during merge conflicts** - @comebackLater
	4. **Staging helps you keep extra local files** - This is for temporary build/environment problems, until a solution is found. __BAD PRACTICE in general__


*****


17. What happens if this is done

	touch a.txt # create a.txt
	git add a.txt #version 1
	modify a.txt 
	git add a.txt #version 2
	# does index store version 1 or just version 2 (or both) ?



18. Remember, a repo is made of commits. Also, the repo and staging area are two different regions. Versions are saved only in commits. The index(aka staging area) does not contain versions. It contains only one copy of each staged file(from the latest stage). In fact, even if a staged file is deleted from the directory, it will end up in the commit.


*****


17. Do *staging index* / *index */ *staging-area* / *cache* all refer to the same thing?
18. Yes. Staging Index is a region, i.e an *area*. Its function is to cache/store a copy of staged files, so it is also called the *cache*.


*****


17. Git displays modified files, even those which have not been staged yet, are these changes saved?
18. No. The working directory and its changes have got nothing to do with the repo. These modification messages(i.e soft tracking) by Git is just a help. It does not affect the repo.

e.g
	touch index.html # file created in working directory
	git add index.html # this is cached at the staging area
	rm index.html # file deleted from working directory
	git commit -m "add index.html" # this is okay, because the commit only has the cached index.html
	
	

