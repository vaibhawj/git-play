# git-play
Playing with git

vibe@Box:~/work/git-play$ git push -u origin master
Username for 'https://github.com': vaibhawj
Password for 'https://vaibhawj@github.com': 
Counting objects: 6, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (6/6), 438 bytes | 0 bytes/s, done.
Total 6 (delta 0), reused 0 (delta 0)
To https://github.com/vaibhawj/git-play.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
vibe@Box:~/work/git-play$ ls
config  src
vibe@Box:~/work/git-play$ git checkout -b feature1
Switched to a new branch 'feature1'
vibe@Box:~/work/git-play$ cd src/
vibe@Box:~/work/git-play/src$ ls
Main.java
vibe@Box:~/work/git-play/src$ gedit Feature1.java
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ git branch
* feature1
  master
vibe@Box:~/work/git-play/src$ git stash --help
vibe@Box:~/work/git-play/src$ 
vibe@Box:~/work/git-play/src$ git stash -u
Saved working directory and index state WIP on feature1: d4f7faf first cut
HEAD is now at d4f7faf first cut
vibe@Box:~/work/git-play/src$ git status
On branch feature1
nothing to commit, working directory clean
vibe@Box:~/work/git-play/src$ ls
Main.java
vibe@Box:~/work/git-play/src$ cd ..
vibe@Box:~/work/git-play$ ls
config  src
vibe@Box:~/work/git-play$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.
vibe@Box:~/work/git-play$ ls
config  src
vibe@Box:~/work/git-play$ git branch
  feature1
* master
vibe@Box:~/work/git-play$ git checkout -b hotfix
Switched to a new branch 'hotfix'
vibe@Box:~/work/git-play$ ls
config  src
vibe@Box:~/work/git-play$ cd src/
vibe@Box:~/work/git-play/src$ ls
Main.java
vibe@Box:~/work/git-play/src$ gedit Main.java 
vibe@Box:~/work/git-play/src$ ls
Main.java
vibe@Box:~/work/git-play/src$ git branch
  feature1
* hotfix
  master
vibe@Box:~/work/git-play/src$ ls
Main.java
vibe@Box:~/work/git-play/src$ cd ..
vibe@Box:~/work/git-play$ ls
config  src
vibe@Box:~/work/git-play$ git status
On branch hotfix
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   src/Main.java

no changes added to commit (use "git add" and/or "git commit -a")
vibe@Box:~/work/git-play$ git commit --help
vibe@Box:~/work/git-play$ git commit -m "bug fixed"
On branch hotfix
Changes not staged for commit:
	modified:   src/Main.java

no changes added to commit
vibe@Box:~/work/git-play$ git status
On branch hotfix
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   src/Main.java

no changes added to commit (use "git add" and/or "git commit -a")
vibe@Box:~/work/git-play$ git add src/Main.java 
vibe@Box:~/work/git-play$ ls
config  src
vibe@Box:~/work/git-play$ git commit -m "bug fixed"
[hotfix 8aa8fbd] bug fixed
 1 file changed, 1 insertion(+), 1 deletion(-)
vibe@Box:~/work/git-play$ git branch
  feature1
* hotfix
  master
vibe@Box:~/work/git-play$ git push --help
vibe@Box:~/work/git-play$ 
vibe@Box:~/work/git-play$ git push
fatal: The current branch hotfix has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin hotfix

vibe@Box:~/work/git-play$ git push -u origin hotfix
Username for 'https://github.com': vj.vaibhaw@gmail.com
Password for 'https://vj.vaibhaw@gmail.com@github.com': 
Counting objects: 4, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 350 bytes | 0 bytes/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/vaibhawj/git-play.git
 * [new branch]      hotfix -> hotfix
Branch hotfix set up to track remote branch hotfix from origin.
vibe@Box:~/work/git-play$ git status
On branch hotfix
Your branch is up-to-date with 'origin/hotfix'.
nothing to commit, working directory clean
vibe@Box:~/work/git-play$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.
vibe@Box:~/work/git-play$ git branch
  feature1
  hotfix
* master
vibe@Box:~/work/git-play$ git merge hotfix
Updating d4f7faf..8aa8fbd
Fast-forward
 src/Main.java | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
vibe@Box:~/work/git-play$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
vibe@Box:~/work/git-play$ git push -u origin master
Username for 'https://github.com': vj.vaibhaw@gmail.com
Password for 'https://vj.vaibhaw@gmail.com@github.com': 
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/vaibhawj/git-play.git
   d4f7faf..8aa8fbd  master -> master
Branch master set up to track remote branch master from origin.
vibe@Box:~/work/git-play$ ls
config  src
vibe@Box:~/work/git-play$ git branch
  feature1
  hotfix
* master
vibe@Box:~/work/git-play$ git checkout feature1
Switched to branch 'feature1'
vibe@Box:~/work/git-play$ git stash --help
vibe@Box:~/work/git-play$ git stash list
stash@{0}: WIP on feature1: d4f7faf first cut
vibe@Box:~/work/git-play$ git stash --help
vibe@Box:~/work/git-play$ 
vibe@Box:~/work/git-play$ git stash apply
Already up-to-date!
On branch feature1
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	src/Feature1.java

nothing added to commit but untracked files present (use "git add" to track)
vibe@Box:~/work/git-play$ ls
config  src
vibe@Box:~/work/git-play$ cd src/
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ cd ..
vibe@Box:~/work/git-play$ git stash
No local changes to save
vibe@Box:~/work/git-play$ ls
config  src
vibe@Box:~/work/git-play$ cd src/
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ git checkout hotfix
Switched to branch 'hotfix'
Your branch is up-to-date with 'origin/hotfix'.
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ git branch
  feature1
* hotfix
  master
vibe@Box:~/work/git-play/src$ git status
On branch hotfix
Your branch is up-to-date with 'origin/hotfix'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	Feature1.java

nothing added to commit but untracked files present (use "git add" to track)
vibe@Box:~/work/git-play/src$ git checkout Feature1
error: pathspec 'Feature1' did not match any file(s) known to git.
vibe@Box:~/work/git-play/src$ git checkout feature1
Switched to branch 'feature1'
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ git branch
* feature1
  hotfix
  master
vibe@Box:~/work/git-play/src$ git status
On branch feature1
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	Feature1.java

nothing added to commit but untracked files present (use "git add" to track)
vibe@Box:~/work/git-play/src$ git add Feature1.java 
vibe@Box:~/work/git-play/src$ git stash
Saved working directory and index state WIP on feature1: d4f7faf first cut
HEAD is now at d4f7faf first cut
vibe@Box:~/work/git-play/src$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.
vibe@Box:~/work/git-play/src$ git branch
  feature1
  hotfix
* master
vibe@Box:~/work/git-play/src$ ls
Main.java
vibe@Box:~/work/git-play/src$ git checkout Feature1
error: pathspec 'Feature1' did not match any file(s) known to git.
vibe@Box:~/work/git-play/src$ git checkout feature1
Switched to branch 'feature1'
vibe@Box:~/work/git-play/src$ ls
Main.java
vibe@Box:~/work/git-play/src$ ls
Main.java
vibe@Box:~/work/git-play/src$ git status
On branch feature1
nothing to commit, working directory clean
vibe@Box:~/work/git-play/src$ git stash list
stash@{0}: WIP on feature1: d4f7faf first cut
stash@{1}: WIP on feature1: d4f7faf first cut
vibe@Box:~/work/git-play/src$ git stash apply 1
fatal: ambiguous argument '1': unknown revision or path not in the working tree.
Use '--' to separate paths from revisions, like this:
'git <command> [<revision>...] -- [<file>...]'
vibe@Box:~/work/git-play/src$ git stash apply --help
vibe@Box:~/work/git-play/src$ git stash apply --1
unknown option: --1
vibe@Box:~/work/git-play/src$ git stash apply 1
fatal: ambiguous argument '1': unknown revision or path not in the working tree.
Use '--' to separate paths from revisions, like this:
'git <command> [<revision>...] -- [<file>...]'
vibe@Box:~/work/git-play/src$ git stash apply
On branch feature1
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   Feature1.java

vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ git status
On branch feature1
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   Feature1.java

vibe@Box:~/work/git-play/src$ git branch
* feature1
  hotfix
  master
vibe@Box:~/work/git-play/src$ git commit -m "feature1 done"
[feature1 0ce00cc] feature1 done
 1 file changed, 9 insertions(+)
 create mode 100644 src/Feature1.java
vibe@Box:~/work/git-play/src$ git push -u origin feature1
Username for 'https://github.com': vj.vaibhaw@gmail.com
Password for 'https://vj.vaibhaw@gmail.com@github.com': 
Counting objects: 4, done.
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 447 bytes | 0 bytes/s, done.
Total 4 (delta 0), reused 0 (delta 0)
To https://github.com/vaibhawj/git-play.git
 * [new branch]      feature1 -> feature1
Branch feature1 set up to track remote branch feature1 from origin.
vibe@Box:~/work/git-play/src$ git status
On branch feature1
Your branch is up-to-date with 'origin/feature1'.
nothing to commit, working directory clean
vibe@Box:~/work/git-play/src$ git branch
* feature1
  hotfix
  master
vibe@Box:~/work/git-play/src$ git status
On branch feature1
Your branch is up-to-date with 'origin/feature1'.
nothing to commit, working directory clean
vibe@Box:~/work/git-play/src$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.
vibe@Box:~/work/git-play/src$ git merge feature1
Merge made by the 'recursive' strategy.
 src/Feature1.java | 9 +++++++++
 1 file changed, 9 insertions(+)
 create mode 100644 src/Feature1.java
vibe@Box:~/work/git-play/src$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
vibe@Box:~/work/git-play/src$ git branch
  feature1
  hotfix
* master
vibe@Box:~/work/git-play/src$ git push -u origin master
Username for 'https://github.com': vj.vaibhaw@gmail.com
Password for 'https://vj.vaibhaw@gmail.com@github.com': 
Counting objects: 3, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 372 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/vaibhawj/git-play.git
   8aa8fbd..3907ec7  master -> master
Branch master set up to track remote branch master from origin.
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ git branch
  feature1
  hotfix
* master
vibe@Box:~/work/git-play/src$ git checkout feature1
Switched to branch 'feature1'
Your branch is up-to-date with 'origin/feature1'.
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ gedit Feature1.java 
vibe@Box:~/work/git-play/src$ git status
On branch feature1
Your branch is up-to-date with 'origin/feature1'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   Feature1.java

no changes added to commit (use "git add" and/or "git commit -a")
vibe@Box:~/work/git-play/src$ git add Feature1.java 
vibe@Box:~/work/git-play/src$ git status
On branch feature1
Your branch is up-to-date with 'origin/feature1'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   Feature1.java

vibe@Box:~/work/git-play/src$ git branch
* feature1
  hotfix
  master
vibe@Box:~/work/git-play/src$ git commit -m "minor bug fixed in feature1"
[feature1 d97637c] minor bug fixed in feature1
 1 file changed, 1 insertion(+), 1 deletion(-)
vibe@Box:~/work/git-play/src$ git push -u origin feature1
Username for 'https://github.com': vj.vaibhaw@gmail.com
Password for 'https://vj.vaibhaw@gmail.com@github.com': 
Counting objects: 4, done.
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 389 bytes | 0 bytes/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/vaibhawj/git-play.git
   0ce00cc..d97637c  feature1 -> feature1
Branch feature1 set up to track remote branch feature1 from origin.
vibe@Box:~/work/git-play/src$ git status
On branch feature1
Your branch is up-to-date with 'origin/feature1'.
nothing to commit, working directory clean
vibe@Box:~/work/git-play/src$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.
vibe@Box:~/work/git-play/src$ git branch
  feature1
  hotfix
* master
vibe@Box:~/work/git-play/src$ git merge --help
vibe@Box:~/work/git-play/src$ git merge feature1
Merge made by the 'recursive' strategy.
 src/Feature1.java | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
vibe@Box:~/work/git-play/src$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
vibe@Box:~/work/git-play/src$ git push -u origin master
Username for 'https://github.com': vj.vaibhaw@gmail.com
Password for 'https://vj.vaibhaw@gmail.com@github.com': 
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/vaibhawj/git-play.git/'
vibe@Box:~/work/git-play/src$ git push -u origin master
Username for 'https://github.com': vj.vaibhaw@gmail.com
Password for 'https://vj.vaibhaw@gmail.com@github.com': 
Counting objects: 3, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 381 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/vaibhawj/git-play.git
   3907ec7..866af1f  master -> master
Branch master set up to track remote branch master from origin.
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Main.java
vibe@Box:~/work/git-play/src$ git branch
  feature1
  hotfix
* master
vibe@Box:~/work/git-play/src$ git checkout -b feature2
Switched to a new branch 'feature2'
vibe@Box:~/work/git-play/src$ git branch
  feature1
* feature2
  hotfix
  master
vibe@Box:~/work/git-play/src$ gedit Feature2.java
vibe@Box:~/work/git-play/src$ ls
Feature1.java  Feature2.java  Main.java
vibe@Box:~/work/git-play/src$ git status
On branch feature2
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	Feature2.java

nothing added to commit but untracked files present (use "git add" to track)
vibe@Box:~/work/git-play/src$ git add Feature2.java 
vibe@Box:~/work/git-play/src$ git status
On branch feature2
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   Feature2.java

vibe@Box:~/work/git-play/src$ git reset Feature
Feature1.java  Feature2.java  
vibe@Box:~/work/git-play/src$ git reset Feature2.java
vibe@Box:~/work/git-play/src$ git status
On branch feature2
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	Feature2.java

nothing added to commit but untracked files present (use "git add" to track)
vibe@Box:~/work/git-play/src$ 
