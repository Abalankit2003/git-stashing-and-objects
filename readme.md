

*****************************BASIC GIT**********************************

git status

1. untracked:- new files that git doesn't yet track

2. modified:- changed files

3. staged:- file is ready to be committed

4. unmodified: unchanged files

5. add:- add new or changed files in your working directory to the Git staging area
i. git add (file name)
ii. git add . (for every file inside the folder)

6. commit:- it is the record of change
i. git commit -m "Message"

7. push:- upload local repo content to remote repo
i. git push origin main

8. init:- used to create a new git repo
i. git init
ii. git remote add origin <-link->
iii. git remote -v
iv. git branch
v. git branch -M main (for changing the name from master to main)
vi. git push origin main
vii. git push -u origin main (it permanently changes inside the origin main only)

9. git checkout <-branch name-> to navigate

10. git checkout -b <-new branch name-> to create new branch

11. git branch -d <-branch name-> to delete branch , we can't delete the branch that we are currently on

Merging code 

1. git diff <-branch name -> to compare commits, branches, files and more

2. git merger <-branch name-> to merge two branches

3. Pull request:- it lets you tell others about changes you have pushed to a branch in a repo on github

12. git pull origin main : -> syncs local repo to remote repo with latest updates

13. git fetch upstream main -> git merge upstream/main : -> The first command helps developers to review the recent commits in the remote main branch. Then, the second one merge the latest commits to local git main branch.

14. Remove-Item ".git" -Force -Recurse -> for removing a folder from git tracking. Simply nullify the git init.

15. git remote remove origin -> To disconnect remote repo to local repo in git.

16. git rev-list --count HEAD -> This command gives the total commits counts.



*****************************GIT OBJECTS**********************************

=> When you use Git to track changes in a project, Git stores information internally using objects. Think of Git objects as the building blocks of how Git manages your files, history, and commits. There are four key types of objects:

Blob (Binary Large Object)
Tree
Commit
Tag


1. Blob => A blob stores the content of a single file. It doesn’t care about the filename or its location, just the content of the file itself.

2. Tree Object => A tree object represents the structure of your project (directories and files). It acts like a folder that stores:
		- References to blobs (for files)
		- References to other tree objects (for directories inside directories)

3. Commit Object => A commit object represents a snapshot of your project at a certain point in time.
			It stores:
				- A reference to a tree object (the state of the project at that moment)
				- Metadata like the author, message, and timestamp
				- Reference to the parent commit (the previous commit, if any)

4. Tag Object => A tag object is used to mark important points in history, like a release version. It’s like a named commit, often used for things like v1.0 or v2.0.


***COMMANDS => 

1. git ls-files --stage => To get the hash of the blob object. Git creates blob objects for the files which it is staged. Use this command just after staging your changes to check for blob objects of the changed file.

2. git cat-file -p 557db03de997 => This will print out the stored content which "557db03de997" is pointing. "557db03de997" is the hash of the file.

3. git log --oneline => Use this command to see the latest commit’s hash. 

4. git cat-file -p e38f3b6 => Run the following to see what’s inside the commit object.

5. git cat-file -p 94fba5fbbf89a51e3c6bfc4bd0f40353e6dbbcc7 => This command will show what is contained in tree object.

6. git rev-list --all --objects => Lists out all objects in git directory.







*****************************STASHING***********************************

=> Stashing stands for temporarily shelves (or stashes) changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on. Stashing is handy if you need to quickly switch context and work on something else, but you're mid-way through a code change and aren't quite ready to commit.

1. git stash => command takes your uncommitted changes (both staged and unstaged), saves them away for later use, and then reverts them from your working copy. 

NOTE:-> the stash is local to your Git repository; stashes are not transferred to the server when you push. Git won't stash changes made to untracked or ignored files.

2. git stash save "Message" => to annotate your stashes with a description.

3. git stash -a => stashes ignored and untracked files too.

4. git stash list => shows all saved stashes.

5. git stash pop => You can reapply previously stashed changes to working directory. Popping your stash removes the changes from your stash and reapplies them to your working copy. It will re-apply the most recently created stash.

6. git stash show => Lists the difference between the working directory content and the recently stashed content. It shows number of lines changed.

7. git stash show -p => Lists all differences with the content that is different between them.

8. git stash drop stash@{1} => drops the stash no. 1 from stashing area.

9. git stash clear => clears all stashes from stashing area.

10. git stash drop stash@{3} => This will remove the stash indexed at 3 from the stashing area.
