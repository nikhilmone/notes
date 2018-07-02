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
