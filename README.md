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
 
-
+print("Bakwass")

