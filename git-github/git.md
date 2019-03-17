## Week 5:
#  Tooling: Git & GitHub

# What is Git?
A tool (software) that allows us to:
keep track of how our code changes over time
collaborate with others in a controllable, ordered manner

## Module Outline

##### Introduction to version management

##### Git architecture and how it works

##### Basic Git commands

##### Git in the real world, giving it a go!

##### Best practice for use

##### Git workflows and project strategy

##### Workflows applied

##### Why version manage?


## Editing files directly on server

Working directly on server drawbacks
no ability to automatically rollback changes
requires you to manage keeping backups and different versions of files high risk!working with multiple contributors is tricky


## Working with version management

Each version of files in the project has a snapshot, and can be reverted to at any point
automatically keeps track of which files have changed and need to be uploaded changes have an audit log, who made what change when

## Version control: the basics

### Example: text document

Multiple people editing the document.
Great, as long as people edit the same document sequentially.
If two people start editing different copies then someone has to manually combine the changes, what happens if the changes overlap?


* (most) operations are local
* rolling back to early snapshot
* creating a branch
* creating a new snapshot
* merging branches*

Reduces requests over network, increases speed+efficiency, allows working offline

## Git has integrity

Everything is check-summed before storage
Snapshots are referred to by that checksum
Impossible to change the contents of any file or directory without Git knowing about it.

Checksumming is SHA-1 hash, producing 40-character string e.g.:
24b9da6552252987aa493b52f8696cd6d3b00373

## Git only adds data

Actions in Git (nearly) only add data to the Git database
It is hard to get the system to do anything that is not undoable or to make it erase data in any way

Only way you can lose or mess up changes is if you haven’t pushed your work yet

Great safety net for trying things out, and rolling back
After you commit a snapshot it is very difficult to lose data, especially if you regularly push to a remote repository.


# Git: the basics

## The language

### repository	 / repo**
project files and a versioning database, in our example this is hosted on GitHub, but can be hosted on any Git server or your local machine

### fetch
fetching file versions and information from central repository server, e.g. GitHub


### checkout
switch your project directory to a certain version of the project, replaces version managed files with the versions from this point in time

### commit
create a point in time version of the current state of the project files

### push
push your snapshots (work), to the central project repository, to allow other people to pull and checkout your changes

### pull

pulling down from the central project repository and updating the branch you are working on

## Basic workflow

## Common workflow

* Make changes
* Commit work
* Push work
* Pull other people's work

### Getting started

#### Getting started

### What are we going to do?

create a project repository on our GitHub accounts
create a project directory on your machine
start version managing it with Git
add a remote repo
start adding files to our project
add and commit those files
push those files to GitHub
make changes to the files and commit them

### To consider: our first commit

There can be only 1 first commit on a project, so you should plan for this to either be:

#### 1) On GitHub
Creating a repository with a README.md or other file in it

##### OR

#### 2) On our computer
Doing our first commit in our project folder


### Steps you'll need to take

make a new project directory
cd to your project folder = type command cd /path/to/project and hit enter

Pro tip: drag folder into terminal to get the path

### Commands we'll need

### Option 1: first commit on GitHub

$ git init
$ git remote add origin {repository URL, starts git@github.com….}
$ git fetch
$ git checkout master
$ git add {filename}
$ git commit -m "adding my first file"
$ git push
	

### Option 2: first commit on your computer
$ git init
$ git remote add origin {repository URL}
$ git add {filename}
$ git commit -m "adding my first file"
$ git push

#### Using the GitHub interface

Now go to GitHub to see that the your file is there.

### Editing files
	
#### Edit, commit, push

Make a change to your files
Then $ git add {filename} to stage that change
Then commit it with $ git commit -m "some message" 
Finally $ git push and go to GitHub to see that the change is reflected there

## Git cheat sheet

$ git init	
initialize (start) git handling in the current directory

$ git remote add origin {repository URL}
add the remote repo location (GitHub)
should be SSH version, starting git@github.com...

$ git fetch
fetches all branches and revisions, to your local machine

$ git checkout master	

change your project code to the most recent snapshot in the master branch

$ git add *
adds all files to be version managed

$ git add {filename}
add a specific file to be version managed

$ git commit -a -m 'message'
creates a point-in-time snapshot of all changed tracked files (-a), with commit message (-m)

$ git commit -m 'message'

creates a point-in-time snapshot of all files that have been added to staging, with commit message (-m)

$ git status

see what state your files are in

$ git rev-parse HEAD

$ git reflog

#### Command line cheat sheet

$ pwd
print working directory, where am I now?

$ cd {directory name}
change/move to working directory

$ mkdir {directory name}
create a new directory

$ git clone {repository URL} {folder to create}

Create a folder, checkout project into it






















