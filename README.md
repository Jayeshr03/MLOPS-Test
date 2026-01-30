# MLOPS-Test

Author - Jayesh R (jayeshr03@gmail.com)

This repo includes my MLOPS knowledge with notes and Projects.


Why MLOps?

So a DevOps engineer deploys software and maintains the CI/CD piplelines, Easy. But it's complex with ML is involved - Data vailditaion( keeps track of what datasets are given to the ML) and Data versioning ( what kind of datasets are given ) and mointroing- Model Drift , Accuracy and Prcision.

Basic workflow - 

DG → EDA → Pre-Processing → Feature Engineering → Feature Selection → Model Training → Evaluation.

Example to understand - 
House pricing :

1. DG - Raw Data like where the house is located and how much does it cost and etc.
2. EDA - We see the use ful stuff like price and size of the house and location.
3. Pre processing - We convert to Computer form
    City → 1
    Town → 0
4. Feature Eng - We build feature - House cost = size x sqft price , small or big house
5. Feature selection - we keep it clean and filter the features - cost,sqft,price imp and rooms is less impactful as sqft says it all.
6. Model Trains - Data is split and the model learns as the size and location is better the price goes up (Linear Regression) .
7. Metrics (Regression):

MAE = 3L

RMSE = 4L

R² = 0.91


Git is a VSC/SCM

- Git and Github is very important for MLops and we need to version all the data set to ML to train.
- Collobration is needed and git/github is useful

Github arc -

**Workspace
Local Repo
Staging
Remote Repo**

Example -

Consider shopping veggis and consider workspace as the shop and Staging as the veggies bag where you can put or remove the veggies and consider Local Repo has the house/fridge where you can do whatever cook throw etc and Remote Repo as the external storage area to keep the vegggies and you can share that with your family and friends.

Consider that you have DG and ESA files in your laptop in order to git to see you have allow it and it takes this files as untracked files and when pushed to staging it's tracked know git knows it has some files to commit abd then once confirmed the git is commited to Local Repo and push it Remote Repo where we know that the issue of it being corrupted is elminated.

Workspace -

git status - let me in there is no git (fatal: not a git repository (or any of the parent directories): .git)

Staging-

git init - Initialized empty Git repository in /Users/admin/Documents/Code/.git/ created and now untracked files comes

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        first.py

nothing added to commit but untracked files present (use "git add" to track)
**admin@admins-MacBook-Pro** Code % git add first.py

Now in staging no commit.

Local repo - 

git commit -m "1st commit" 
[main (root-commit) 41f1d79] 1st commit
 1 file changed, 9 insertions(+)
 create mode 100644 first.py

 Now we commit with comment for reference on what the commit was about. 

 Changed and did an another commit -

 admin@admins-MacBook-Pro Code % git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   first.py

no changes added to commit (use "git add" and/or "git commit -a")
admin@admins-MacBook-Pro Code % git add first.py 
admin@admins-MacBook-Pro Code % git status      
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   first.py

admin@admins-MacBook-Pro Code % git commit -m "2st commit"
[main 3596935] 2st commit
 1 file changed, 1 insertion(+), 1 deletion(-)
admin@admins-MacBook-Pro Code % git status                
On branch main
nothing to commit, working tree clean
admin@admins-MacBook-Pro Code % git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

nothing added to commit but untracked files present (use "git add" to track)

.gitignore is a file to tell the git to ignore files and not to track it.

 We did the third commit.

** SEEING COMMITS - **

**- git log**

 will show all the commits
 
commit ********************** (SHA ID - UNQIUE ID) (HEAD -> main(Recent is refered as a HEAD))
Author: Jayesh03 <jayesh03@gmail.com>
Date:   Wed Jan 28 22:25:50 2026 +0530

    3rd commit - gitignore

commit ******************
Author: Jayesh03 <jayesh03@gmail.com>
Date:   Wed Jan 28 22:16:54 2026 +0530

    2st commit

commit *******************
Author: Jayesh03 <jayesh03@gmail.com>
Date:   Wed Jan 28 22:12:15 2026 +0530

    1st commit

**- git log --oneline**

In one line we get all the info

**- git log --stat**

  .gitignore | 1 + ( this means you have added line)
 1 file changed, 1 insertion(+)

**- git log -p**

You get detailed with code.

****- git show *****9****

Shows the specfic commit

**git diff **

changes made within staging before commit

diff --git a/first.py b/first.py
index 8268192..e1eb692 100644
--- a/first.py
+++ b/first.py
@@ -4,6 +4,6 @@ print("Thanks")
 
 print("Adding second line for reference")



If we have to checkout or go back to a line of commond -

admin@admins-MacBook-Pro Code % git log --oneline 
8d37da4 (HEAD -> main) 3rd commit - gitignore
3596935 2st commit
41f1d79 1st commit
admin@admins-MacBook-Pro Code %** git checkout 3596935**
M       first.py
Note: switching to '3596935'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 3596935 2st commit
 
-
+print("Bakwass")


NOW BRANCHING - 

admin@admins-MacBook-Pro Code % git log --oneline
1f45d7e (HEAD -> main) 7 -second commit  main work after helper and branching
86c36bd 6 - main work after helper and branching
8d37da4 3rd commit - gitignore
3596935 2st commit
41f1d79 1st commit

Going to a Helper branch -

admin@admins-MacBook-Pro Code % **git checkout helper**
Switched to branch 'helper'
admin@admins-MacBook-Pro Code % git log --online
fatal: unrecognized argument: --online
admin@admins-MacBook-Pro Code % git log --oneline
1ee5274 (HEAD -> helper) 5 - helper work finished and branching
9af64cb 4 - helper work started and branching
8d37da4 3rd commit - gitignore
3596935 2st commit
41f1d79 1st commit

Now, if we are in the main and see log it only show the commit made there and once you come to branch it shows only commit made there 
MAIN _ (admin@admins-MacBook-Pro Code % git log --oneline
1f45d7e (HEAD -> main) 7 -second commit  main work after helper and branching
86c36bd 6 - main work after helper and branching
8d37da4 3rd commit - gitignore
3596935 2st commit
41f1d79 1st commit     Now this is in main)

HELPER - (admin@admins-MacBook-Pro Code % git log --oneline
1ee5274 (HEAD -> helper) 5 - helper work finished and branching
9af64cb 4 - helper work started and branching
8d37da4 3rd commit - gitignore
3596935 2st commit
41f1d79 1st commit - Now this is in branch helper)

To retify that we have --all which shows all.


admin@admins-MacBook-Pro Code % git log --oneline --all
1f45d7e (main) 7 -second commit  main work after helper and branching
86c36bd 6 - main work after helper and branching
1ee5274 (HEAD -> helper) 5 - helper work finished and branching
9af64cb 4 - helper work started and branching
8d37da4 3rd commit - gitignore
3596935 2st commit
41f1d79 1st commit


This is shown for full branching -

admin@admins-MacBook-Pro Code % **git log --oneline --all --graph**
* 1f45d7e (main) 7 -second commit  main work after helper and branching
* 86c36bd 6 - main work after helper and branching
| * 1ee5274 (HEAD -> helper) 5 - helper work finished and branching
| * 9af64cb 4 - helper work started and branching
|/  
* 8d37da4 3rd commit - gitignore
* 3596935 2st commit
* 41f1d79 1st commit

NWO LET"S DELETE A BRANCH --

admin@admins-MacBook-Pro Code % ****git branch -d helper ****
error: Cannot delete branch 'helper' checked out at '/Users/admin/Documents/Code'

It's throwing error because we are in that branch and Github realease we havent merged it.

admin@admins-MacBook-Pro Code % git checkout main                                       
Switched to branch 'main'

-D we delete it - it's like --force.
admin@admins-MacBook-Pro Code % git branch -D helper 
Deleted branch helper (was 1ee5274).

<img width="3036" height="1056" alt="image" src="https://github.com/user-attachments/assets/392b7081-6d80-4752-887a-28c5e7ccf8c2" />

Now we create HELPER 2 to study **MERGING**

<img width="3182" height="1394" alt="image" src="https://github.com/user-attachments/assets/e5f58831-a4b3-4a23-9b23-a9df959c42c7" />

NOW WE HAVE DONE MERGING 
admin@admins-MacBook-Pro Code % git checkout main  
Switched to branch 'main'
admin@admins-MacBook-Pro Code % git merge main   
Already up to date.
admin@admins-MacBook-Pro Code % git merge helper2
Updating 1f45d7e..dc5f665
Fast-forward
 helper2.py | 3 +++
 1 file changed, 3 insertions(+)
 create mode 100644 helper2.py
admin@admins-MacBook-Pro Code % git log --oneline
dc5f665 (HEAD -> main, helper2) 9 - second commit of helper2
bbb7fa7 8 - Firsdt commit of helper2
1f45d7e 7 -second commit  main work after helper and branching
86c36bd 6 - main work after helper and branching
8d37da4 3rd commit - gitignore
3596935 2st commit
41f1d79 1st commit
admin@admins-MacBook-Pro Code % 

ONLY WITH MAIN we have merge.

NOW WE HAVE THE BRANCH AND COMMIT TO MAIN

NOW WE DO A DIFFCULT MERGE WHERE 

<img width="2350" height="1196" alt="image" src="https://github.com/user-attachments/assets/43078c53-259b-4c7e-80b0-d5bac0e27346" />

AS you can see the after 7 we didn't have any merging so it was easy so we make it diffcult  by creeating a coimmit in 9th to branch 10 and 11 to main.

I made a mistake and created both on branch so i did - 

**git reset --soft HEAD~1** — what it means

1️⃣ git reset

Moves Git’s HEAD pointer (the current commit) backward.

Think of it as:

“Pretend the last commit never happened.”

2️⃣ --soft

This is the important part.

--soft means:

❌ Commit is removed

✅ All changes are kept

✅ Changes stay staged (in the index)

So nothing is lost.

3️⃣ HEAD~1

Means:

“One commit before the current commit”

If your history is:

A → B → C (HEAD)


HEAD~1 points to:

A → B (HEAD)


Commit C is removed.

What actually happens after the command
Before:
Commit 1
Commit 2   ← HEAD

After git reset --soft HEAD~1:
Commit 1   ← HEAD


But:

Files from Commit 2 are still there

They are staged

git status will show:

Changes to be committed

When should you use this?

Use it when:

You committed too early

You want to edit files

You want to combine commits

You want to change the commit message

Quick comparison 🧠
Command	Commit removed	Changes kept	Staged?
--soft	✅	✅	✅
--mixed (default)	✅	✅	❌
--hard	✅	❌	❌

<img width="3384" height="1184" alt="image" src="https://github.com/user-attachments/assets/31ccef24-808f-4547-9289-b08a67f3196f" />

We have 10 as branch and 11 in main --

We have conflit I have code in same lines for both(one from branch and one when done from main) so when merging 

admin@admins-MacBook-Pro Code % git merge final
Auto-merging first.py
CONFLICT (content): Merge conflict in first.py
Automatic merge failed; fix conflicts and then commit the result.

<<<<<<< HEAD
print("FINAL STUPID")
=======
print( "AFTER BRANCHING FINAL")
>>>>>>> final
>>>>>>
Get this which  tells and gives options 

<img width="1270" height="368" alt="image" src="https://github.com/user-attachments/assets/36930c16-2aec-4c08-aef5-f7dd662de492" />


So this tells that current that is main or incoming that is branch or both should stay or compare

If I did both stay --

admin@admins-MacBook-Pro Code % git log --oneline --all --graph                 
***** 17ccc64 (HEAD -> main) 11 - FINAL commit of helper2
| * 95b6e06 (final) 10 - firsFINAL commit of helper2
| * 8b1eeb3 10 - firsFINAL commit of helper2
| * e031b94 10 - firsFINAL commit of helper2************
|/  
* dc5f665 9 - second commit of helper2
* bbb7fa7 8 - Firsdt commit of helper2
* 1f45d7e 7 -second commit  main work after helper and branching
* 86c36bd 6 - main work after helper and branching
* 8d37da4 3rd commit - gitignore
* 3596935 2st commit
* 41f1d79 1st commit
* 
admin@admins-MacBook-Pro Code % git merge final
Auto-merging first.py
CONFLICT (content): Merge conflict in first.py
Automatic merge failed; fix conflicts and then commit the re sult.
admin@admins-MacBook-Pro Code % git log --oneline
**17ccc64 (HEAD -> main) 11 - FINAL commit of helper2
dc5f665 9 - second commit of helper2******
bbb7fa7 8 - Firsdt commit of helper2
1f45d7e 7 -second commit  main work after helper and branching
86c36bd 6 - main work after helper and branching
8d37da4 3rd commit - gitignore
3596935 2st commit
41f1d79 1st commit

  If you see the 10th commit is now merged to 11th

****REMOTE REPO
********  

Still now we worked till commit.

Now we can do a remote repo -

<img width="3084" height="1638" alt="image" src="https://github.com/user-attachments/assets/d0809aa4-a4e7-41b7-9b50-d38dea8acf48" />

Now we will push to a repo

We get the https and then do git remote add origin

Now created a friends repo 


admin@admins-MacBook-Pro Git-Friend-Repo % git add .
admin@admins-MacBook-Pro Git-Friend-Repo % git commit -m "added friend work"
[main 931432b] added friend work
 1 file changed, 3 insertions(+)
 create mode 100644 addednew.py
admin@admins-MacBook-Pro Git-Friend-Repo % git branch     
* main
admin@admins-MacBook-Pro Git-Friend-Repo % git push commit main             
fatal: 'commit' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
admin@admins-MacBook-Pro Git-Friend-Repo % git push origin main             
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 14 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 286 bytes | 286.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:Jayeshr03/Git-Friend-Repo.git
   e1b40eb..931432b  main -> main
admin@admins-MacBook-Pro Git-Friend-Repo % git pull origin main
From github.com:Jayeshr03/Git-Friend-Repo
 * branch            main       -> FETCH_HEAD
Updating 931432b..186866d
Fast-forward
 example.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 example.txt


Basically Pull means all the updates will be updated
and push will push all the changes made.
