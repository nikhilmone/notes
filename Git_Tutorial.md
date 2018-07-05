# Set up GIT environment

- Install git client on your machine.
- Create a global configuration using below:

```
$ git config --global --list
fatal: unable to read config file '/Users/nikhil/.gitconfig': No such file or directory

$ git config --global user.name "Nikhil Mone"

Nikhils-MacBook-Air:git_tutorial nikhil$ git config --global --list
user.name=Nikhil Mone
user.email=nikhilmone7@gmail.com
Nikhils-MacBook-Air:git_tutorial nikhil$ cat ~/.gitconfig 
[user]
	name = Nikhil Mone
	email = nikhilmone7@gmail.com
Nikhils-MacBook-Air:git_tutorial nikhil$ git config --global core.editor vim
Nikhils-MacBook-Air:git_tutorial nikhil$ git config --global help.autocorrect 1
Nikhils-MacBook-Air:git_tutorial nikhil$ 
Nikhils-MacBook-Air:git_tutorial nikhil$ 
Nikhils-MacBook-Air:git_tutorial nikhil$ 
Nikhils-MacBook-Air:git_tutorial nikhil$ git statsu
WARNING: You called a Git command named 'statsu', which does not exist.
Continuing in 0.1 seconds, assuming that you meant 'status'.
fatal: Not a git repository (or any of the parent directories): .git


help.autocorrect <number> waits for those many seconds before doing an auto-correct
setting it to `0` means disabling it.
```

```
Nikhils-MacBook-Air:git_tutorial nikhil$ git config --global color.ui auto
Nikhils-MacBook-Air:git_tutorial nikhil$ git config --global core.autocrlf input # use 'true' for windows true | false | input
Nikhils-MacBook-Air:git_tutorial nikhil$ 
Nikhils-MacBook-Air:git_tutorial nikhil$ 
Nikhils-MacBook-Air:git_tutorial nikhil$ 
Nikhils-MacBook-Air:git_tutorial nikhil$ cat ~/.gitconfig 
[user]
	name = Nikhil Mone
	email = nikhilmone7@gmail.com
[core]
	editor = vim
	autocrlf = input
[help]
	autocorrect = 1
[color]
	ui = auto
Nikhils-MacBook-Air:git_tutorial nikhil$ git config --global --list
user.name=Nikhil Mone
user.email=nikhilmone7@gmail.com
core.editor=vim
core.autocrlf=input
help.autocorrect=1
color.ui=auto
```

# Config setup at repo level:

```
Nikhils-MacBook-Air:git_tutorial nikhil$ git clone https://github.com/nikhilmone/notes.git
Cloning into 'notes'...
remote: Counting objects: 21, done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 21 (delta 0), reused 0 (delta 0), pack-reused 18
Unpacking objects: 100% (21/21), done.
Nikhils-MacBook-Air:git_tutorial nikhil$ cd notes/
Nikhils-MacBook-Air:notes nikhil$ ls -al
total 48
drwxr-xr-x   6 nikhil  staff    192 Jul  2 17:45 .
drwxr-xr-x   3 nikhil  staff     96 Jul  2 17:45 ..
drwxr-xr-x  12 nikhil  staff    384 Jul  2 17:45 .git
-rw-r--r--   1 nikhil  staff   1912 Jul  2 17:45 Git_Tutorial.md
-rw-r--r--   1 nikhil  staff  16216 Jul  2 17:45 README.md
-rw-r--r--   1 nikhil  staff   1530 Jul  2 17:45 docker-compose.yaml
Nikhils-MacBook-Air:notes nikhil$ 
Nikhils-MacBook-Air:notes nikhil$ 
Nikhils-MacBook-Air:notes nikhil$ 
Nikhils-MacBook-Air:notes nikhil$ 
Nikhils-MacBook-Air:notes nikhil$ cat .git/config 
[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
	ignorecase = true
	precomposeunicode = true
[remote "origin"]
	url = https://github.com/nikhilmone/notes.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
	remote = origin
	merge = refs/heads/master
Nikhils-MacBook-Air:notes nikhil$ git config --list
credential.helper=osxkeychain
user.name=Nikhil Mone
user.email=nikhilmone7@gmail.com
core.editor=vim
core.autocrlf=input
help.autocorrect=1
color.ui=auto
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
remote.origin.url=https://github.com/nikhilmone/notes.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.master.remote=origin
branch.master.merge=refs/heads/master
```

## set username and unset it

```
Nikhils-MacBook-Air:notes nikhil$ git config user.name nm
Nikhils-MacBook-Air:notes nikhil$ 
Nikhils-MacBook-Air:notes nikhil$ 
Nikhils-MacBook-Air:notes nikhil$ 
Nikhils-MacBook-Air:notes nikhil$ git config --list
credential.helper=osxkeychain
user.name=Nikhil Mone
user.email=nikhilmone7@gmail.com
core.editor=vim
core.autocrlf=input
help.autocorrect=1
color.ui=auto
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
remote.origin.url=https://github.com/nikhilmone/notes.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.master.remote=origin
branch.master.merge=refs/heads/master
user.name=nm
Nikhils-MacBook-Air:notes nikhil$ git config --unset user.name
Nikhils-MacBook-Air:notes nikhil$ git config --list
credential.helper=osxkeychain
user.name=Nikhil Mone
user.email=nikhilmone7@gmail.com
core.editor=vim
core.autocrlf=input
help.autocorrect=1
color.ui=auto
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
remote.origin.url=https://github.com/nikhilmone/notes.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.master.remote=origin
branch.master.merge=refs/heads/master
```

# Working with git locally

```
Nikhils-MacBook-Air:git_tutorial nikhil$ mkdir GitFundamentals
Nikhils-MacBook-Air:git_tutorial nikhil$ 
Nikhils-MacBook-Air:git_tutorial nikhil$ 
Nikhils-MacBook-Air:git_tutorial nikhil$ 
Nikhils-MacBook-Air:git_tutorial nikhil$ cd GitFundamentals/
Nikhils-MacBook-Air:GitFundamentals nikhil$ git init
Initialized empty Git repository in /Users/nikhil/git_tutorial/GitFundamentals/.git/
Nikhils-MacBook-Air:GitFundamentals nikhil$ ls -al
total 0
drwxr-xr-x  3 nikhil  staff   96 Jul  2 18:08 .
drwxr-xr-x  4 nikhil  staff  128 Jul  2 18:08 ..
drwxr-xr-x  9 nikhil  staff  288 Jul  2 18:08 .git
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ echo "Hello Git" > README.md
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ cat README.md 
Hello Git
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	README.md

nothing added to commit but untracked files present (use "git add" to track)
Nikhils-MacBook-Air:GitFundamentals nikhil$ git add README.md 
Nikhils-MacBook-Air:GitFundamentals nikhil$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   README.md

Nikhils-MacBook-Air:GitFundamentals nikhil$ git commit
[master (root-commit) abb3a65] Add README file
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ git status
On branch master
nothing to commit, working tree clean

Nikhils-MacBook-Air:GitFundamentals nikhil$ git log
commit abb3a654f302170e90df270f28fca27611418d4e (HEAD -> master)
Author: Nikhil Mone <nikhilmone7@gmail.com>
Date:   Mon Jul 2 18:10:32 2018 +0530

    Add README file
```

Make changes:

```
Nikhils-MacBook-Air:GitFundamentals nikhil$ vim README.md 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
Nikhils-MacBook-Air:GitFundamentals nikhil$ git add -u    #adds the updated files
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   README.md

Nikhils-MacBook-Air:GitFundamentals nikhil$ git commit -m "update README"
[master f005eb8] update README
 1 file changed, 1 insertion(+)
Nikhils-MacBook-Air:GitFundamentals nikhil$ git log
commit f005eb8c3a175d2233bd17f1eb2046fdd865b66f (HEAD -> master)
Author: Nikhil Mone <nikhilmone7@gmail.com>
Date:   Mon Jul 2 18:15:42 2018 +0530

    update README

commit abb3a654f302170e90df270f28fca27611418d4e
Author: Nikhil Mone <nikhilmone7@gmail.com>
Date:   Mon Jul 2 18:10:32 2018 +0530

    Add README file
```

## Checking history and doing diff

```
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ git diff abb3a6..f005eb
diff --git a/README.md b/README.md
index 9f4d96d..cbdb028 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,2 @@
 Hello Git
+from Nikhil
Nikhils-MacBook-Air:GitFundamentals nikhil$ git diff f005eb..abb3a6
diff --git a/README.md b/README.md
index cbdb028..9f4d96d 100644
--- a/README.md
+++ b/README.md
@@ -1,2 +1 @@
 Hello Git
-from Nikhil
Nikhils-MacBook-Air:GitFundamentals nikhil$ git diff HEAD~1..HEAD
diff --git a/README.md b/README.md
index 9f4d96d..cbdb028 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,2 @@
 Hello Git
+from Nikhil
Nikhils-MacBook-Air:GitFundamentals nikhil$ git diff HEAD..HEAD~1
diff --git a/README.md b/README.md
index cbdb028..9f4d96d 100644
--- a/README.md
+++ b/README.md
@@ -1,2 +1 @@
 Hello Git
-from Nikhil
Nikhils-MacBook-Air:GitFundamentals nikhil$ git diff HEAD~1..
diff --git a/README.md b/README.md
index 9f4d96d..cbdb028 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,2 @@
 Hello Git
+from Nikhil
Nikhils-MacBook-Air:GitFundamentals nikhil$ touch file1.md file2.md
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	file1.md
	file2.md

nothing added to commit but untracked files present (use "git add" to track)
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ git add -u
Nikhils-MacBook-Air:GitFundamentals nikhil$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	file1.md
	file2.md

nothing added to commit but untracked files present (use "git add" to track)
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ 
Nikhils-MacBook-Air:GitFundamentals nikhil$ git add -A
Nikhils-MacBook-Air:GitFundamentals nikhil$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   file1.md
	new file:   file2.md

Nikhils-MacBook-Air:GitFundamentals nikhil$ git commit -m "add new files"
[master fbbd5ab] add new files
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file1.md
 create mode 100644 file2.md
Nikhils-MacBook-Air:GitFundamentals nikhil$ git log
commit fbbd5abd710984a40343f20f423c0a324480a3be (HEAD -> master)
Author: Nikhil Mone <nikhilmone7@gmail.com>
Date:   Mon Jul 2 18:26:40 2018 +0530

    add new files

commit f005eb8c3a175d2233bd17f1eb2046fdd865b66f
Author: Nikhil Mone <nikhilmone7@gmail.com>
Date:   Mon Jul 2 18:15:42 2018 +0530

    update README

commit abb3a654f302170e90df270f28fca27611418d4e
Author: Nikhil Mone <nikhilmone7@gmail.com>
Date:   Mon Jul 2 18:10:32 2018 +0530

    Add README file
Nikhils-MacBook-Air:GitFundamentals nikhil$ git diff HEAD~1..
diff --git a/file1.md b/file1.md
new file mode 100644
index 0000000..e69de29
diff --git a/file2.md b/file2.md
new file mode 100644
index 0000000..e69de29
```
