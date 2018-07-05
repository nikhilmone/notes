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

Nikhil :  /d/Git/Git_Fundamentals (master)
$ touch temp1.txt temp2.txt

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        temp1.txt
        temp2.txt

nothing added to commit but untracked files present (use "git add" to track)

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git clean
fatal: clean.requireForce defaults to true and neither -i, -n, nor -f given; refusing to clean

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git clean -f
Removing temp1.txt
Removing temp2.txt

Nikhil :  /d/Git/Git_Fundamentals (master)
$ ls-al
bash: ls-al: command not found

Nikhil :  /d/Git/Git_Fundamentals (master)
$ ls -al
total 34
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 12:17 ./
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 ../
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 12:16 .git/
-rw-r--r-- 1 NI387801 1049089   55 Jul  3 12:11 Dockerfile
-rw-r--r-- 1 NI387801 1049089   23 Jul  3 11:24 hosts
-rw-r--r-- 1 NI387801 1049089  850 Jul  3 11:24 index.jsp
-rw-r--r-- 1 NI387801 1049089  538 Jul  3 12:13 Jenkinsfile
-rw-r--r-- 1 NI387801 1049089  317 Jul  3 11:24 load_images.sh
-rw-r--r-- 1 NI387801 1049089  400 Jul  3 11:24 package.json
-rw-r--r-- 1 NI387801 1049089  163 Jul  3 11:24 playbook.yaml
-rw-r--r-- 1 NI387801 1049089 2274 Jul  3 11:24 test.json
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 tests/
-rw-r--r-- 1 NI387801 1049089 9717 Jul  3 11:24 wiprologo.jpg

Nikhil :  /d/Git/Git_Fundamentals (master)
$

Nikhil :  /d/Git/Git_Fundamentals (master)
$


Nikhil :  /d/Git/Git_Fundamentals (master)
$

Nikhil :  /d/Git/Git_Fundamentals (master)
$ touch temp1.txt temp2.txt

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        temp1.txt
        temp2.txt

nothing added to commit but untracked files present (use "git add" to track)

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git clean
fatal: clean.requireForce defaults to true and neither -i, -n, nor -f given; refusing to clean

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git clean -n
Would remove temp1.txt
Would remove temp2.txt

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git clean -f
Removing temp1.txt
Removing temp2.txt


=====================================


Nikhil :  /d/Git/Git_Fundamentals (master)
$ git log --oneline
0c8a02a Add new file
8193b9c Add new directory
411083c Update Jenkinsfile
4535aa8 Update Jenkinsfile
5d51a33 Add test file
8eff1f3 Update Jenkinsfile
39f45bc Update Jenkinsfile
30d7daa Update Jenkinsfile
5aa20bb Update Jenkinsfile
1a5c597 Added Jenkinsfile
1daacfd Update Jenkinsfile
193bf26 Added Jenkinsfile
91582bf Added Jenkinsfile
2610227 update demo
69480ac change in index
b5d8d3d yeah
301d5f3 demo to eKYC team
1c0ca64 change in index for demo to Mukund
237638a change in index
94ba95d change in index page
98c224b change index.jsp
e120874 change index file
74e04ae modify index.jsp
67be3db remove white spaces.
bb28307 add automation
3d79449 add code
059acd0 Add new file

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git log --oneline | wc -l
27

Nikhil :  /d/Git/Git_Fundamentals (master)
$


Nikhil :  /d/Git/Git_Fundamentals (master)
$

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git log --graph
* commit 0c8a02adac1d6a4bef9165136185dc03d85ecc52
| Author: Nikhil Mone <nikhil.mone@wipro.com>
| Date:   Fri Jun 22 07:54:17 2018 -0400
|
|     Add new file
|
* commit 8193b9ce7ea668146d5619dc7b58e8b29385070a
| Author: Nikhil Mone <nikhil.mone@wipro.com>
| Date:   Fri Jun 22 07:52:08 2018 -0400
|
|     Add new directory
|
* commit 411083c1d7037f7f7e447402cff7084771514e49
| Author: Nikhil Mone <nikhil.mone@wipro.com>
| Date:   Fri Jun 22 07:44:04 2018 -0400
|
|     Update Jenkinsfile
|
* commit 4535aa8c689fb0cca4f1c52e785eeb58e063ed5b
| Author: Nikhil Mone <nikhil.mone@wipro.com>
| Date:   Fri Jun 22 06:39:21 2018 -0400
|
|     Update Jenkinsfile
|
* commit 5d51a336240dbd5a8546f692237c1bc26dc524f5
| Author: Nikhil Mone <nikhil.mone@wipro.com>
| Date:   Fri Jun 22 03:36:09 2018 -0400
|
|     Add test file
|
* commit 8eff1f331f23e49c1a53e6512594dc133aea1572
| Author: Nikhil Mone <nikhil.mone@wipro.com>
| Date:   Fri Jun 22 03:35:15 2018 -0400
|
|     Update Jenkinsfile
|
* commit 39f45bc9721ffa3befddc22cc0798c2bda853491
| Author: Nikhil Mone <nikhil.mone@wipro.com>
| Date:   Wed Jun 13 02:35:23 2018 -0400
|
|     Update Jenkinsfile
|

Nikhil :  /d/Git/Git_Fundamentals (master)
$


Nikhil :  /d/Git/Git_Fundamentals (master)
$

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git log --shortlog
fatal: unrecognized argument: --shortlog

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git shortlog
Nikhil Mone (24):
      Add new file
      add code
      add automation
      remove white spaces.
      modify index.jsp
      change index file
      change index.jsp
      change in index page
      change in index
      change in index for demo to Mukund
      demo to eKYC team
      yeah
      change in index
      update demo
      Update Jenkinsfile
      Update Jenkinsfile
      Update Jenkinsfile
      Update Jenkinsfile
      Update Jenkinsfile
      Add test file
      Update Jenkinsfile
      Update Jenkinsfile
      Add new directory
      Add new file

nikhil (3):
      Added Jenkinsfile
      Added Jenkinsfile
      Added Jenkinsfile




ksjdbvksjdvjk	

$ Git show HEAD
commit 0c8a02adac1d6a4bef9165136185dc03d85ecc52
Author: Nikhil Mone <nikhil.mone@wipro.com>
Date:   Fri Jun 22 07:54:17 2018 -0400

    Add new file

diff --git a/package.json b/package.json
new file mode 100644
index 0000000..4d0f438
--- /dev/null
+++ b/package.json
@@ -0,0 +1,15 @@
+{
+  "name": "postman-newman-jenkins",
+  "version": "1.0.0",
+  "description": "My Test Project",
+  "directories": {
+    "tests": "tests"
+  },
+  "scripts": {
+    "newman-tests": "newman run unit_tests/my-collection.postman_collection.json --reporters cli,junit --reporter-junit-export newman.xml --insecure"
+  },
+  "author": "Test Author",
+  "dependencies": {
+    "newman": "^3.5.2"
+  }
+}
\ No newline at end of file




Nikhil :  /d/Git/Git_Fundamentals (master)
$ git remote
origin

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git remote -v
origin  http://10.210.16.204/container-factory/test.git (fetch)
origin  http://10.210.16.204/container-factory/test.git (push)

Nikhil :  /d/Git/Git_Fundamentals (master)
$ cat .git/config
[core]
        repositoryformatversion = 0
        filemode = false
        bare = false
        logallrefupdates = true
        symlinks = false
        ignorecase = true
[remote "origin"]
        url = http://10.210.16.204/container-factory/test.git
        fetch = +refs/heads/*:refs/remotes/origin/*
[gui]
        wmstate = zoomed
        geometry = 887x427+78+78 321 297

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git branch
* master

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git branch -r
  origin/master

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git tag

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git remote -v
origin  http://10.210.16.204/container-factory/test.git (fetch)
origin  http://10.210.16.204/container-factory/test.git (push)

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git remote add origin http://xyz.git

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git fetch

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git fetch origin


$ git merge origin/master               ##### Merging the remote branch with my local master branch
Updating 0c8a02a..b82be94
Fast-forward
 Jenkinsfile | 15 +++++++++------
 1 file changed, 9 insertions(+), 6 deletions(-)

Nikhil :  /d/Git/Git_Fundamentals (master)
$ ls -al
total 34
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 12:04 ./
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 ../
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 12:04 .git/
-rw-r--r-- 1 NI387801 1049089   55 Jul  3 12:11 Dockerfile
-rw-r--r-- 1 NI387801 1049089   23 Jul  3 11:24 hosts
-rw-r--r-- 1 NI387801 1049089  850 Jul  3 11:24 index.jsp
-rw-r--r-- 1 NI387801 1049089  640 Jul  4 12:04 Jenkinsfile
-rw-r--r-- 1 NI387801 1049089  317 Jul  3 11:24 load_images.sh
-rw-r--r-- 1 NI387801 1049089  400 Jul  3 11:24 package.json
-rw-r--r-- 1 NI387801 1049089  163 Jul  3 11:24 playbook.yaml
-rw-r--r-- 1 NI387801 1049089 2274 Jul  3 11:24 test.json
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 tests/
-rw-r--r-- 1 NI387801 1049089 9717 Jul  3 11:24 wiprologo.jpg


### git fetch; git merge origin/master   ===  git pull

git branch --set-upstream master origin/master        ### set my master to track master of origin (remote)

git pull 

or do : git pull origin master # to pull master of the origin

############

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git tag -a v1.0
fatal: tag 'v1.0' already exists

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git tag -a v1.0_with_message

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git tag -s v1.0_signed
gpg: directory `/c/Users/NI387801/.gnupg' created
gpg: new configuration file `/c/Users/NI387801/.gnupg/gpg.conf' created
gpg: WARNING: options in `/c/Users/NI387801/.gnupg/gpg.conf' are not yet active during this run
gpg: keyring `/c/Users/NI387801/.gnupg/secring.gpg' created
gpg: keyring `/c/Users/NI387801/.gnupg/pubring.gpg' created
gpg: skipped "Nikhil Mone <nikhil.mone@wipro.com>": secret key not available
gpg: signing failed: secret key not available
error: gpg failed to sign the data
error: unable to sign the tag
The tag message has been left in .git/TAG_EDITMSG


$ git tag v1.0_signed

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git tag
v1.0
v1.0_signed
v1.0_with_message

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git tag -v v1.0_signed
error: v1.0_signed: cannot verify a non-tag object of type commit.

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git show v1.0
commit cccd464c21e10931305fd35608130dc7d8b5222a
Author: Nikhil Mone <nikhil.mone@wipro.com>
Date:   Wed Jul 4 14:04:59 2018 +0530

    add README

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..5db0c2b
--- /dev/null
+++ b/README.md
@@ -0,0 +1 @@
+This is a Container Factory demo.

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git push
Everything up-to-date

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git push --tags
Counting objects: 1, done.
Writing objects: 100% (1/1), 181 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To http://10.210.16.204/container-factory/test.git
 * [new tag]         v1.0 -> v1.0
 * [new tag]         v1.0_signed -> v1.0_signed
 * [new tag]         v1.0_with_message -> v1.0_with_message


 $ git log --graph --oneline --all --decorate
* cccd464 (HEAD -> master, tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master) add README
* b82be94 Update Jenkinsfile
* 0c8a02a Add new file
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile
* 30d7daa Update Jenkinsfile
* 5aa20bb Update Jenkinsfile
* 1a5c597 Added Jenkinsfile
* 1daacfd Update Jenkinsfile
* 193bf26 Added Jenkinsfile
* 91582bf Added Jenkinsfile
* 2610227 update demo
* 69480ac change in index
* b5d8d3d yeah
* 301d5f3 demo to eKYC team
* 1c0ca64 change in index for demo to Mukund
* 237638a change in index
* 94ba95d change in index page
* 98c224b change index.jsp
* e120874 change index file
* 74e04ae modify index.jsp
* 67be3db remove white spaces.
* bb28307 add automation
* 3d79449 add code
* 059acd0 Add new file

 
Creating Alias for git commands:

$ git config --global alias.lga "log --graph --oneline --all --decorate"

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git lga
* cccd464 (HEAD -> master, tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master) add README
* b82be94 Update Jenkinsfile
* 0c8a02a Add new file
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile
* 30d7daa Update Jenkinsfile
* 5aa20bb Update Jenkinsfile
* 1a5c597 Added Jenkinsfile
* 1daacfd Update Jenkinsfile
* 193bf26 Added Jenkinsfile
* 91582bf Added Jenkinsfile
* 2610227 update demo
* 69480ac change in index
* b5d8d3d yeah
* 301d5f3 demo to eKYC team
* 1c0ca64 change in index for demo to Mukund
* 237638a change in index
* 94ba95d change in index page
* 98c224b change index.jsp
* e120874 change index file
* 74e04ae modify index.jsp
* 67be3db remove white spaces.
* bb28307 add automation
* 3d79449 add code
* 059acd0 Add new file

==================================================

$ cat ~/.gitconfig
[filter "lfs"]
        clean = git-lfs clean -- %f
        smudge = git-lfs smudge -- %f
        process = git-lfs filter-process
        required = true
[merge]
        tool = kdiff3
[diff]
        guitool = kdiff3
[core]
        editor = \"C:/Program Files (x86)/GitExtensions/GitExtensions.exe\" fileeditor
        autocrlf = True
[user]
        name = Nikhil Mone
        email = nikhil.mone@wipro.com
[gui]
        recentrepo = D:/Git/Git_Fundamentals
[help]
        autocorrect = 1
[color]
        ui = auto
[alias]
        lga = log --graph --oneline --all --decorate


================================================

## Branching


$ git branch feature1

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git checkout feature1
Switched to branch 'feature1'

Nikhil :  /d/Git/Git_Fundamentals (feature1)
$ git lga
* cccd464 (HEAD -> feature1, tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master, master) add README
* b82be94 Update Jenkinsfile
* 0c8a02a Add new file
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile
* 30d7daa Update Jenkinsfile
* 5aa20bb Update Jenkinsfile
* 1a5c597 Added Jenkinsfile
* 1daacfd Update Jenkinsfile
* 193bf26 Added Jenkinsfile
* 91582bf Added Jenkinsfile
* 2610227 update demo
* 69480ac change in index
* b5d8d3d yeah
* 301d5f3 demo to eKYC team
* 1c0ca64 change in index for demo to Mukund
* 237638a change in index
* 94ba95d change in index page
* 98c224b change index.jsp
* e120874 change index file
* 74e04ae modify index.jsp
* 67be3db remove white spaces.
* bb28307 add automation
* 3d79449 add code
* 059acd0 Add new file

Nikhil :  /d/Git/Git_Fundamentals (feature1)
$ echo "Feature one" >> README.md

Nikhil :  /d/Git/Git_Fundamentals (feature1)
$ git status
On branch feature1
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

Nikhil :  /d/Git/Git_Fundamentals (feature1)
$ git commit -am "added feature"
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
[feature1 warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
b299cd8] added feature
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
 1 file changed, 1 insertion(+)

Nikhil :  /d/Git/Git_Fundamentals (feature1)
$ git status
On branch feature1
nothing to commit, working tree clean

Nikhil :  /d/Git/Git_Fundamentals (feature1)
$ git lga
* b299cd8 (HEAD -> feature1) added feature
* cccd464 (tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master, master) add README
* b82be94 Update Jenkinsfile
* 0c8a02a Add new file
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile
* 30d7daa Update Jenkinsfile
* 5aa20bb Update Jenkinsfile
* 1a5c597 Added Jenkinsfile
* 1daacfd Update Jenkinsfile
* 193bf26 Added Jenkinsfile
* 91582bf Added Jenkinsfile
* 2610227 update demo
* 69480ac change in index
* b5d8d3d yeah
* 301d5f3 demo to eKYC team
* 1c0ca64 change in index for demo to Mukund
* 237638a change in index
* 94ba95d change in index page
* 98c224b change index.jsp
* e120874 change index file
* 74e04ae modify index.jsp
* 67be3db remove white spaces.
* bb28307 add automation
* 3d79449 add code
* 059acd0 Add new file

Nikhil :  /d/Git/Git_Fundamentals (feature1)
$ gti checkout master
bash: gti: command not found

Nikhil :  /d/Git/Git_Fundamentals (feature1)
$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git lga
* b299cd8 (feature1) added feature
* cccd464 (HEAD -> master, tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master) add README
* b82be94 Update Jenkinsfile
* 0c8a02a Add new file
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile
* 30d7daa Update Jenkinsfile
* 5aa20bb Update Jenkinsfile
* 1a5c597 Added Jenkinsfile
* 1daacfd Update Jenkinsfile
* 193bf26 Added Jenkinsfile
* 91582bf Added Jenkinsfile
* 2610227 update demo
* 69480ac change in index
* b5d8d3d yeah
* 301d5f3 demo to eKYC team
* 1c0ca64 change in index for demo to Mukund
* 237638a change in index
* 94ba95d change in index page
* 98c224b change index.jsp
* e120874 change index file
* 74e04ae modify index.jsp
* 67be3db remove white spaces.
* bb28307 add automation
* 3d79449 add code
* 059acd0 Add new file

## Create branch for a particular commit

$ git branch fix123 8193b9c

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git checkout fix123
Switched to branch 'fix123'

Nikhil :  /d/Git/Git_Fundamentals (fix123)
$ ls -al
total 33
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 14:52 ./
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 ../
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 14:52 .git/
-rw-r--r-- 1 NI387801 1049089   55 Jul  3 12:11 Dockerfile
-rw-r--r-- 1 NI387801 1049089   23 Jul  3 11:24 hosts
-rw-r--r-- 1 NI387801 1049089  850 Jul  3 11:24 index.jsp
-rw-r--r-- 1 NI387801 1049089  538 Jul  4 14:52 Jenkinsfile
-rw-r--r-- 1 NI387801 1049089  317 Jul  3 11:24 load_images.sh
-rw-r--r-- 1 NI387801 1049089  163 Jul  3 11:24 playbook.yaml
-rw-r--r-- 1 NI387801 1049089 2274 Jul  3 11:24 test.json
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 tests/
-rw-r--r-- 1 NI387801 1049089 9717 Jul  3 11:24 wiprologo.jpg

Nikhil :  /d/Git/Git_Fundamentals (fix123)
$ vi README.md

Nikhil :  /d/Git/Git_Fundamentals (fix123)
$ git status
On branch fix123
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        README.md

nothing added to commit but untracked files present (use "git add" to track)

Nikhil :  /d/Git/Git_Fundamentals (fix123)
$ git commit -am "fixed bug #123"
On branch fix123
Untracked files:
        README.md

nothing added to commit but untracked files present

Nikhil :  /d/Git/Git_Fundamentals (fix123)
$

Nikhil :  /d/Git/Git_Fundamentals (fix123)
$

Nikhil :  /d/Git/Git_Fundamentals (fix123)
$ git add README.md
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.

Nikhil :  /d/Git/Git_Fundamentals (fix123)
$ git commit -am "fixed bug #123"
[fix123 c160935] fixed bug #123
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

 
 Nikhil :  /d/Git/Git_Fundamentals (fix123)
$ git lga
* c160935 (HEAD -> fix123) fixed bug #123
| * b299cd8 (feature1) added feature
| * cccd464 (tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master, master) add README
| * b82be94 Update Jenkinsfile
| * 0c8a02a Add new file
|/
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile
* 30d7daa Update Jenkinsfile
* 5aa20bb Update Jenkinsfile
* 1a5c597 Added Jenkinsfile
* 1daacfd Update Jenkinsfile
* 193bf26 Added Jenkinsfile
* 91582bf Added Jenkinsfile
* 2610227 update demo
* 69480ac change in index
* b5d8d3d yeah
* 301d5f3 demo to eKYC team
* 1c0ca64 change in index for demo to Mukund
* 237638a change in index
* 94ba95d change in index page
* 98c224b change index.jsp
* e120874 change index file
* 74e04ae modify index.jsp
* 67be3db remove white spaces.
* bb28307 add automation
* 3d79449 add code
* 059acd0 Add new file



## Rename a branch:

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git branch -m fix123 bug123

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git lga
* c160935 (bug123) fixed bug #123
| * b299cd8 (feature1) added feature
| * cccd464 (HEAD -> master, tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master) add README
| * b82be94 Update Jenkinsfile
| * 0c8a02a Add new file
|/
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile

## Delete branch
Nikhil :  /d/Git/Git_Fundamentals (master)
$ git branch -d bug123
error: The branch 'bug123' is not fully merged.
If you are sure you want to delete it, run 'git branch -D bug123'.


## Create and checkout branch:

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git checkout -b feature2
Switched to a new branch 'feature2'


## Recover a deleted branch:

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git branch -D bug123
Deleted branch bug123 (was c160935).

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git reflog
cccd464 HEAD@{0}: checkout: moving from master to feature2
cccd464 HEAD@{1}: checkout: moving from fix123 to master
c160935 HEAD@{2}: commit: fixed bug #123
8193b9c HEAD@{3}: checkout: moving from master to fix123
cccd464 HEAD@{4}: checkout: moving from feature1 to master
b299cd8 HEAD@{5}: commit: added feature
cccd464 HEAD@{6}: checkout: moving from master to feature1
cccd464 HEAD@{7}: commit: add README
b82be94 HEAD@{8}: merge origin/master: Fast-forward
0c8a02a HEAD@{9}: reset: moving to HEAD~1
4d4e56a HEAD@{10}: commit: Signed-off-by: Nikhil Mone <nikhil.mone@wipro.com>
0c8a02a HEAD@{11}: reset: moving to HEAD~1
b82be94 HEAD@{12}: reset: moving to HEAD~1
6bb0f09 HEAD@{13}: commit: add changes
b82be94 HEAD@{14}:

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git branch bug1234 c160935

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ ls -al
total 35
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 15:06 ./
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 ../
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 15:12 .git/
-rw-r--r-- 1 NI387801 1049089   55 Jul  3 12:11 Dockerfile
-rw-r--r-- 1 NI387801 1049089   23 Jul  3 11:24 hosts
-rw-r--r-- 1 NI387801 1049089  850 Jul  3 11:24 index.jsp
-rw-r--r-- 1 NI387801 1049089  640 Jul  4 15:06 Jenkinsfile
-rw-r--r-- 1 NI387801 1049089  317 Jul  3 11:24 load_images.sh
-rw-r--r-- 1 NI387801 1049089  400 Jul  4 15:06 package.json
-rw-r--r-- 1 NI387801 1049089  163 Jul  3 11:24 playbook.yaml
-rw-r--r-- 1 NI387801 1049089   35 Jul  4 15:06 README.md
-rw-r--r-- 1 NI387801 1049089 2274 Jul  3 11:24 test.json
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 tests/
-rw-r--r-- 1 NI387801 1049089 9717 Jul  3 11:24 wiprologo.jpg

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ cat README.md
This is a Container Factory demo.

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git checkout bug1234
Switched to branch 'bug1234'

Nikhil :  /d/Git/Git_Fundamentals (bug1234)
$ cat README.md
this is a fix #123

Nikhil :  /d/Git/Git_Fundamentals (bug1234)
$ git show HEAD
commit c160935f537de106d0ca628d95ead7d605204c68
Author: Nikhil Mone <nikhil.mone@wipro.com>
Date:   Wed Jul 4 14:54:05 2018 +0530

    fixed bug #123

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..93ecdc3
--- /dev/null
+++ b/README.md
@@ -0,0 +1 @@
+this is a fix #123

Nikhil :  /d/Git/Git_Fundamentals (bug1234)


30 Days GC removes the dangling branches and you may loose the change.
========================



Stash your changes and apply/pop them:

apply: your changes are moved back to the files however, stash list contains it.
pop: changes are moved back and stash is cleared.

$ git checkout feature2
Switched to branch 'feature2'

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ echo "Feature 2 changes" >> README.md

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$


Nikhil :  /d/Git/Git_Fundamentals (feature2)
$


Nikhil :  /d/Git/Git_Fundamentals (feature2)
$

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git status
On branch feature2
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
Saved working directory and index state WIP on feature2: cccd464 add README
HEAD is now at cccd464 add README

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ cat README.md
This is a Container Factory demo.

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash list
stash@{0}: WIP on feature2: cccd464 add README

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git checkout bug123
error: pathspec 'bug123' did not match any file(s) known to git.

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git checkout bug1234
Switched to branch 'bug1234'

Nikhil :  /d/Git/Git_Fundamentals (bug1234)
$ echo "Fix to bug #1234" >> README.md

Nikhil :  /d/Git/Git_Fundamentals (bug1234)
$ cat README.md
this is a fix #123
Fix to bug #1234

Nikhil :  /d/Git/Git_Fundamentals (bug1234)
$ git commit -am "bug #1234 is fixed"
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
[bug1234 warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
8869064] bug #1234 is fixed
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
 1 file changed, 1 insertion(+)

Nikhil :  /d/Git/Git_Fundamentals (bug1234)
$ git lga
* 8869064 (HEAD -> bug1234) bug #1234 is fixed
* c160935 fixed bug #123
| *   734c209 (refs/stash) WIP on feature2: cccd464 add README
| |\
| | * 1c44b18 index on feature2: cccd464 add README
| |/
| | * b299cd8 (feature1) added feature
| |/
| * cccd464 (tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master, master, feature2) add README
| * b82be94 Update Jenkinsfile
| * 0c8a02a Add new file
|/
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile
* 30d7daa Update Jenkinsfile
* 5aa20bb Update Jenkinsfile
* 1a5c597 Added Jenkinsfile
* 1daacfd Update Jenkinsfile
* 193bf26 Added Jenkinsfile
* 91582bf Added Jenkinsfile
* 2610227 update demo
* 69480ac change in index
* b5d8d3d yeah
* 301d5f3 demo to eKYC team
* 1c0ca64 change in index for demo to Mukund
* 237638a change in index
* 94ba95d change in index page
* 98c224b change index.jsp
* e120874 change index file
* 74e04ae modify index.jsp
* 67be3db remove white spaces.
* bb28307 add automation
* 3d79449 add code
* 059acd0 Add new file

Nikhil :  /d/Git/Git_Fundamentals (bug1234)
$ git checkout feature2
Switched to branch 'feature2'

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash apply
On branch feature2
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ cat README.md
This is a Container Factory demo.
Feature 2 changes

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash list
stash@{0}: WIP on feature2: cccd464 add README

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git reset --hard HEAD
HEAD is now at cccd464 add README

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash list
stash@{0}: WIP on feature2: cccd464 add README

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ cat README.md
This is a Container Factory demo.

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash pop
On branch feature2
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (734c209ccc357cf226adc609a461fc5f63a31354)

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ cat README.md
This is a Container Factory demo.
Feature 2 changes

## Make some more changes and stash them, drop the stash.. create a branch from the stash:

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ vi feature2.txt

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash
Saved working directory and index state WIP on feature2: cccd464 add README
HEAD is now at cccd464 add README

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ ls -al
total 36
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 15:35 ./
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 ../
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 15:35 .git/
-rw-r--r-- 1 NI387801 1049089   55 Jul  3 12:11 Dockerfile
-rw-r--r-- 1 NI387801 1049089   28 Jul  4 15:35 feature2.txt
-rw-r--r-- 1 NI387801 1049089   23 Jul  3 11:24 hosts
-rw-r--r-- 1 NI387801 1049089  850 Jul  3 11:24 index.jsp
-rw-r--r-- 1 NI387801 1049089  640 Jul  4 15:21 Jenkinsfile
-rw-r--r-- 1 NI387801 1049089  317 Jul  3 11:24 load_images.sh
-rw-r--r-- 1 NI387801 1049089  400 Jul  4 15:21 package.json
-rw-r--r-- 1 NI387801 1049089  163 Jul  3 11:24 playbook.yaml
-rw-r--r-- 1 NI387801 1049089   35 Jul  4 15:35 README.md
-rw-r--r-- 1 NI387801 1049089 2274 Jul  3 11:24 test.json
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 tests/
-rw-r--r-- 1 NI387801 1049089 9717 Jul  3 11:24 wiprologo.jpg

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git add feature2.txt
warning: LF will be replaced by CRLF in feature2.txt.
The file will have its original line endings in your working directory.

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash
Saved working directory and index state WIP on feature2: cccd464 add README
HEAD is now at cccd464 add README

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git status
On branch feature2
nothing to commit, working tree clean

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ ls -al
total 35
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 15:36 ./
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 ../
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 15:37 .git/
-rw-r--r-- 1 NI387801 1049089   55 Jul  3 12:11 Dockerfile
-rw-r--r-- 1 NI387801 1049089   23 Jul  3 11:24 hosts
-rw-r--r-- 1 NI387801 1049089  850 Jul  3 11:24 index.jsp
-rw-r--r-- 1 NI387801 1049089  640 Jul  4 15:21 Jenkinsfile
-rw-r--r-- 1 NI387801 1049089  317 Jul  3 11:24 load_images.sh
-rw-r--r-- 1 NI387801 1049089  400 Jul  4 15:21 package.json
-rw-r--r-- 1 NI387801 1049089  163 Jul  3 11:24 playbook.yaml
-rw-r--r-- 1 NI387801 1049089   35 Jul  4 15:35 README.md
-rw-r--r-- 1 NI387801 1049089 2274 Jul  3 11:24 test.json
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 tests/
-rw-r--r-- 1 NI387801 1049089 9717 Jul  3 11:24 wiprologo.jpg

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash list
stash@{0}: WIP on feature2: cccd464 add README
stash@{1}: WIP on feature2: cccd464 add README

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash drop
Dropped refs/stash@{0} (7c69a5eea9cd7ce8691481613da7cc85efb32b0b)

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash list
stash@{0}: WIP on feature2: cccd464 add README

Nikhil :  /d/Git/Git_Fundamentals (feature2)
$ git stash branch feature2-additional
Switched to a new branch 'feature2-additional'
On branch feature2-additional
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (717de2e2c1768b4912af5cc85b47aa4f953575cb)

Nikhil :  /d/Git/Git_Fundamentals (feature2-additional)
$ git commit -am "added additional features to feature 2"
[feature2-additional 1a738a6] added additional features to feature 2
 1 file changed, 1 insertion(+)

 =========
 
 Merging changes
 
Nikhil :  /d/Git/Git_Fundamentals (feature2-additional)
$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.

Nikhil :  /d/Git/Git_Fundamentals (master)
$ ls -al
total 35
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 15:42 ./
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 ../
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 15:42 .git/
-rw-r--r-- 1 NI387801 1049089   55 Jul  3 12:11 Dockerfile
-rw-r--r-- 1 NI387801 1049089   23 Jul  3 11:24 hosts
-rw-r--r-- 1 NI387801 1049089  850 Jul  3 11:24 index.jsp
-rw-r--r-- 1 NI387801 1049089  640 Jul  4 15:21 Jenkinsfile
-rw-r--r-- 1 NI387801 1049089  317 Jul  3 11:24 load_images.sh
-rw-r--r-- 1 NI387801 1049089  400 Jul  4 15:21 package.json
-rw-r--r-- 1 NI387801 1049089  163 Jul  3 11:24 playbook.yaml
-rw-r--r-- 1 NI387801 1049089   35 Jul  4 15:42 README.md
-rw-r--r-- 1 NI387801 1049089 2274 Jul  3 11:24 test.json
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 tests/
-rw-r--r-- 1 NI387801 1049089 9717 Jul  3 11:24 wiprologo.jpg

Nikhil :  /d/Git/Git_Fundamentals (master)
$ cat README.md
This is a Container Factory demo.

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git lga
* 1a738a6 (feature2-additional) added additional features to feature 2
| * 8869064 (bug1234) bug #1234 is fixed
| * c160935 fixed bug #123
| | * b299cd8 (feature1) added feature
| |/
|/|
* | cccd464 (HEAD -> master, tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master, feature2) add README
* | b82be94 Update Jenkinsfile
* | 0c8a02a Add new file
|/
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile
* 30d7daa Update Jenkinsfile
* 5aa20bb Update Jenkinsfile
* 1a5c597 Added Jenkinsfile
* 1daacfd Update Jenkinsfile
* 193bf26 Added Jenkinsfile
* 91582bf Added Jenkinsfile
* 2610227 update demo
* 69480ac change in index
* b5d8d3d yeah
* 301d5f3 demo to eKYC team
* 1c0ca64 change in index for demo to Mukund
* 237638a change in index
* 94ba95d change in index page
* 98c224b change index.jsp
* e120874 change index file
* 74e04ae modify index.jsp
* 67be3db remove white spaces.
* bb28307 add automation
* 3d79449 add code
* 059acd0 Add new file

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git merge feature1
Updating cccd464..b299cd8
Fast-forward
 README.md | 1 +
 1 file changed, 1 insertion(+)

Nikhil :  /d/Git/Git_Fundamentals (master)
$ cat README.md
This is a Container Factory demo.
Feature one

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git lga
* 1a738a6 (feature2-additional) added additional features to feature 2
| * 8869064 (bug1234) bug #1234 is fixed
| * c160935 fixed bug #123
| | * b299cd8 (HEAD -> master, feature1) added feature
| |/
|/|
* | cccd464 (tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master, feature2) add README
* | b82be94 Update Jenkinsfile
* | 0c8a02a Add new file
|/
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile
* 30d7daa Update Jenkinsfile
* 5aa20bb Update Jenkinsfile
* 1a5c597 Added Jenkinsfile
* 1daacfd Update Jenkinsfile
* 193bf26 Added Jenkinsfile
* 91582bf Added Jenkinsfile
* 2610227 update demo
* 69480ac change in index
* b5d8d3d yeah
* 301d5f3 demo to eKYC team
* 1c0ca64 change in index for demo to Mukund
* 237638a change in index
* 94ba95d change in index page
* 98c224b change index.jsp
* e120874 change index file
* 74e04ae modify index.jsp
* 67be3db remove white spaces.
* bb28307 add automation
* 3d79449 add code
* 059acd0 Add new file

### delete the branch post merge

$ git branch -d feature1
Deleted branch feature1 (was b299cd8).


### Resolving the conflicts:

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git merge feature2-additional
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ cat README.md
This is a Container Factory demo.
<<<<<<< HEAD
Feature one
=======
Feature 2 changes
>>>>>>> feature2-additional

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ git mergetool
Merging:
README.md

Normal merge conflict for 'README.md':
  {local}: modified file
  {remote}: modified file
The merge tool kdiff3 is not available as 'kdiff3'

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ ls -al
total 51
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 16:02 ./
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 ../
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 16:01 .git/
-rw-r--r-- 1 NI387801 1049089   55 Jul  3 12:11 Dockerfile
-rw-r--r-- 1 NI387801 1049089   23 Jul  3 11:24 hosts
-rw-r--r-- 1 NI387801 1049089  850 Jul  3 11:24 index.jsp
-rw-r--r-- 1 NI387801 1049089  640 Jul  4 15:21 Jenkinsfile
-rw-r--r-- 1 NI387801 1049089  317 Jul  3 11:24 load_images.sh
-rw-r--r-- 1 NI387801 1049089  400 Jul  4 15:21 package.json
-rw-r--r-- 1 NI387801 1049089  163 Jul  3 11:24 playbook.yaml
-rw-r--r-- 1 NI387801 1049089   67 Jul  4 16:02 README.md
-rw-r--r-- 1 NI387801 1049089   67 Jul  4 16:02 README.md.BACKUP.5772.md
-rw-r--r-- 1 NI387801 1049089   35 Jul  4 16:02 README.md.BASE.5772.md
-rw-r--r-- 1 NI387801 1049089   48 Jul  4 16:02 README.md.LOCAL.5772.md
-rw-r--r-- 1 NI387801 1049089   54 Jul  4 16:02 README.md.REMOTE.5772.md
-rw-r--r-- 1 NI387801 1049089  119 Jul  4 15:58 README_BACKUP_11216.md
-rw-r--r-- 1 NI387801 1049089  119 Jul  4 15:48 README_BACKUP_17856.md
-rw-r--r-- 1 NI387801 1049089  119 Jul  4 15:47 README_BACKUP_2856.md
-rw-r--r-- 1 NI387801 1049089   35 Jul  4 15:58 README_BASE_11216.md
-rw-r--r-- 1 NI387801 1049089   35 Jul  4 15:53 README_BASE_17856.md
-rw-r--r-- 1 NI387801 1049089   35 Jul  4 15:48 README_BASE_2856.md
-rw-r--r-- 1 NI387801 1049089   48 Jul  4 15:58 README_LOCAL_11216.md
-rw-r--r-- 1 NI387801 1049089   48 Jul  4 15:53 README_LOCAL_17856.md
-rw-r--r-- 1 NI387801 1049089   48 Jul  4 15:48 README_LOCAL_2856.md
-rw-r--r-- 1 NI387801 1049089   54 Jul  4 15:58 README_REMOTE_11216.md
-rw-r--r-- 1 NI387801 1049089   54 Jul  4 15:53 README_REMOTE_17856.md
-rw-r--r-- 1 NI387801 1049089   54 Jul  4 15:48 README_REMOTE_2856.md
-rw-r--r-- 1 NI387801 1049089 2274 Jul  3 11:24 test.json
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 tests/
-rw-r--r-- 1 NI387801 1049089 9717 Jul  3 11:24 wiprologo.jpg

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$


Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$


Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ cat README.md.BACKUP.5772.md
This is a Container Factory demo.
Feature one
Feature 2 changes

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ cat README.md.REMOTE.5772.md
This is a Container Factory demo.
Feature 2 changes

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ cat README_REMOTE_17856.md
This is a Container Factory demo.
Feature 2 changes

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ cat README.md
This is a Container Factory demo.
Feature one
Feature 2 changes

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
You have unmerged paths.
  (fix conflicts and run "git commit")

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        README.md.BACKUP.5772.md
        README.md.BASE.5772.md
        README.md.LOCAL.5772.md
        README.md.REMOTE.5772.md
        README_BACKUP_11216.md
        README_BACKUP_17856.md
        README_BACKUP_2856.md
        README_BASE_11216.md
        README_BASE_17856.md
        README_BASE_2856.md
        README_LOCAL_11216.md
        README_LOCAL_17856.md
        README_LOCAL_2856.md
        README_REMOTE_11216.md
        README_REMOTE_17856.md
        README_REMOTE_2856.md

no changes added to commit (use "git add" and/or "git commit -a")

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ git diff --cached
* Unmerged path README.md

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ git add README.md

Nikhil :  /d/Git/Git_Fundamentals (master|MERGING)
$ git commit -m "resolved the merge conflicts"
[master d97d665] resolved the merge conflicts

Nikhil :  /d/Git/Git_Fundamentals (master)
$ rm  README.md.* README_*

Nikhil :  /d/Git/Git_Fundamentals (master)
$ ls -al
total 35
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 16:06 ./
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 ../
drwxr-xr-x 1 NI387801 1049089    0 Jul  4 16:06 .git/
-rw-r--r-- 1 NI387801 1049089   55 Jul  3 12:11 Dockerfile
-rw-r--r-- 1 NI387801 1049089   23 Jul  3 11:24 hosts
-rw-r--r-- 1 NI387801 1049089  850 Jul  3 11:24 index.jsp
-rw-r--r-- 1 NI387801 1049089  640 Jul  4 15:21 Jenkinsfile
-rw-r--r-- 1 NI387801 1049089  317 Jul  3 11:24 load_images.sh
-rw-r--r-- 1 NI387801 1049089  400 Jul  4 15:21 package.json
-rw-r--r-- 1 NI387801 1049089  163 Jul  3 11:24 playbook.yaml
-rw-r--r-- 1 NI387801 1049089   67 Jul  4 16:02 README.md
-rw-r--r-- 1 NI387801 1049089 2274 Jul  3 11:24 test.json
drwxr-xr-x 1 NI387801 1049089    0 Jul  3 11:24 tests/
-rw-r--r-- 1 NI387801 1049089 9717 Jul  3 11:24 wiprologo.jpg

Nikhil :  /d/Git/Git_Fundamentals (master)
$ git lga
*   d97d665 (HEAD -> master) resolved the merge conflicts
|\
| * 1a738a6 (feature2-additional) added additional features to feature 2
* | b299cd8 added feature
|/
* cccd464 (tag: v1.0_with_message, tag: v1.0_signed, tag: v1.0, origin/master, feature2) add README
* b82be94 Update Jenkinsfile
* 0c8a02a Add new file
| * 8869064 (bug1234) bug #1234 is fixed
| * c160935 fixed bug #123
|/
* 8193b9c Add new directory
* 411083c Update Jenkinsfile
* 4535aa8 Update Jenkinsfile
* 5d51a33 Add test file
* 8eff1f3 Update Jenkinsfile
* 39f45bc Update Jenkinsfile
* 30d7daa Update Jenkinsfile
* 5aa20bb Update Jenkinsfile
* 1a5c597 Added Jenkinsfile
* 1daacfd Update Jenkinsfile
* 193bf26 Added Jenkinsfile
* 91582bf Added Jenkinsfile
* 2610227 update demo
* 69480ac change in index
* b5d8d3d yeah
* 301d5f3 demo to eKYC team
* 1c0ca64 change in index for demo to Mukund
* 237638a change in index
* 94ba95d change in index page
* 98c224b change index.jsp
* e120874 change index file
* 74e04ae modify index.jsp
* 67be3db remove white spaces.
* bb28307 add automation
* 3d79449 add code
* 059acd0 Add new file


==================================



