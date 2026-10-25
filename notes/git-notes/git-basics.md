1) Git - a version control tool installed on your system
2) Github - online platform that hosts git repo and supports collab
3) repository - project + it's version history
4) commit - saved snapshot of your tracked changes
5) merge - combines changes from one branch to another

Edit -> git add -> git commit -> git push

commands :
1) pwd (present working directory)
2) git --version (which version of git is installed on your system)
3) git status (shows modified, staged and unstaged files)
4) git branch (lists local branches)
5) git remote -v (shows configured remote repo URLs)
6) To clone existing repo use -
git clone give the remote repo url
cd your repo

** dont run git init inside an existing cloned repo. Cloning already sets up git and normally configures origin **

** if git remote -v returns nothing in an existing local repo then need to configure the remote before pushing **

CONFIGURE GIT IDENTITY 

git config --global user.name "Aakriti"
git config --global user.email "aakritiacademics@gmail.com"
git config --global --list 

BASIC COMMANDS

mkdir git-practice
cd git-practice
vi git-basics.txt
I am learning Git
:wq
cat git-basics.txt
git status
git add git-basics.txt
git status
git commit -m "initial commit"
git status
git log --oneline  (shows history like new commit and its short hash)

git add (add one particular file)
git add . (adds all files)
git diff (shows unstaged changes)
git diff --staged (shows staged changes compared with the previous commit)
git log --oneline (shows compact commit history)
git show (displays details of a commit)


BRANCHES -

1) main - stable version of your project
2) develop - integration branch where completed work is combined
3) feature - a branch for a specific task - it lets you experiment without directly changing the shared development branch

git branch (shows all branch)
git branch -a (list local and remote tracking branches)
git branch develop (create a develop branch)
git switch develop (switch to develop branch)
git switch -c develop (create and switch to develop branch)


MERGING 

combine changes from one branch to another.You normally switch to branch that should receive the changes first.

eg : want to merge feature work into develop 

git switch develop
git merge feature
git log --oneline --graph --all
git status

Note : local merge doesnt automatically update Github. You need to push so -
git push origin develop


git remote -v (list remote URLs)
git push ( sends local commits to remote branch )
git fetch origin ( download remote updates without merging them into your current branch)
git pull (fetches updates and integrates them into your current branch)


PULL REQUESTS 

github collaboration feature for proposing changes and having them reviewed before merging 

1) create a feature branch
2) commit your changes
3) push the feature branch
4) open a PR
5) review and merge


.gitignore

some files should not be committed such as temporary files, logs, local environment files and secrets

create .gitignore in the repo root


UNDO MISTAKES

git restore --staged filename (removes it from staging without discarding its working tree)
git restore filename (replaces the file with its index version and uncommitted edits are lost
git revert HEAD (creates a new commit reversing the last commit)
