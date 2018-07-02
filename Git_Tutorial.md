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
