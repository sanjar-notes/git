# Relative Commit References
Created Monday 09 November 2020

Relative Commit References
--------------------------
We have seen that commits can be referenced using SHA, tags, branches and HEAD. But sometimes, we'll want to reference a commit w.r.t another commit. e.g the commit before the last, or 2nd before the last.

This is achieved using some special characters called 'Ancestry References':

* ^ - indicates parent of commit. No args taken.
* ~n - indicates nth parent of commit. Takes n as arg, default arg is 1.


e.g
Parent of the current(latest) commit

* HEAD^
* HEAD~
* HEAD~1

Grandparent of the current(latest) commit

* HEAD^^
* HEAD~2

Great-grandparent of the current(latest) commit

* HEAD^^^
* HEAD~3


* What's the difference between ^ and ~, except that one is repetitive?
	* With a merge commit, the ^ reference is used for first parent, while ^2 indicates the second parent(which was the merger). ~ has no such meaning, it is just for the ancestry level.
* HEAD~0 is the same as just HEAD.
* More examples:

	* 9ec05ca (HEAD -> master) Revert "Set page heading to "Quests & Crusades""
	* db7e87a Set page heading to "Quests & Crusades"
	*   796ddb0 Merge branch 'heading-update'
	|\  
	| * 4c9749e (heading-update) Set page heading to "Crusade"
	* | 0c5975a Set page heading to "Quest"
	|/  
	*   1a56a81 Merge branch 'sidebar'
	|\  
	| * f69811c (sidebar) Update sidebar with favorite movie
	| * e6c65a6 Add new sidebar content
	* | e014d91 (footer) Add links to social media
	* | 209752a Improve site heading for SEO
	* | 3772ab1 Set background color for page
	|/  
	* 5bfe5e7 Add starting HTML structure
	* 6fa5f34 Add .gitignore file
	* a879849 Add header to blog
	* 94de470 Initial commit
	

* HEAD^ and HEAD~1 - db7e87a
* HEAD^^ and HEAD~2 - 796ddb0
* HEAD^^^ and HEAD~3 - 0c5975a
* HEAD^^^2 and HEAD~2^2 - 4c9749e
* HEAD~6 - 209752a
* HEAD~4^2 - f69811c


