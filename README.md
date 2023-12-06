## Git Remote

In Git, the term remote is concerned with the remote repository. It is a shared repository that all team members use to exchange their changes. A remote repository is stored on a code hosting service like an internal server, GitHub, Subversion, and more. In the case of a local repository, a remote typically does not provide a file tree of the project's current state; as an alternative, it only consists of the .git versioning data.

The developers can perform many operations with the remote server. These operations can be a clone, fetch, push, pull, and more. Consider the below image:

![git-remote.png]git-remote.png)

## The benefits of  Git Remote:
• git remote  lets you create, view, and delete connections to other repositories.

• Remote connections are more like bookmarks rather than direct links into other repositories Instead of providing real-time access to another repository.

• by using  git remote we can use as convenient names that can be used to reference a not-so-convenient URL.

• Git remote  helps you to manage the set of repository whose branches you track.

• perform the sync operations required to keep the local repository updated as per the central repository and also to update the changes made by the developer in the local repository on the central repository

## To Check your Remote

To check the configuration of the remote server, run the git remote command. The git remote command allows accessing the connection between remote and local. If you want to see the original existence of your cloned repository, use the git remote command. It can be used as:

**git remote**

The given command is providing the remote name as the origin. **Origin** is the default name for the remote server, which is given by Git.
  
Git remote supports a specific option -v to show the URLs that Git has stored as a short name. These short names are used during the reading and write operation. Here, -v stands for verbose. We can use --verbose in place of -v. It is used as:

**git remote -v** 

The above output is providing available remote connections. If a repository contains more than one remote connection, this command will list them all.


**Git Remote Add** When we fetch a repository implicitly, git adds a remote for the repository. Also, we can explicitly add a remote for a repository. We can add a remote as a shot nickname or short name. To add remote as a short name, follow the below command:

 **git remote add <short name><remote URL>**



To add a new remote, use the git remote add command on the terminal, in the directory your
repository is stored at.
The git remote add command takes two arguments:
1. A remote name, for example, **origin*
2. A remote URL, for example, **https://<your-git-service-address>/user/repo.git*
   
**git remote add origin https://<your-git-service-address>/owner/repository.git**


## Clone a repository

The git clone command is used to copy an existing Git repository from a server to the local
machine.
For example, to clone a GitHub project:
cd <path where you'd like the clone to create a directory>

**git clone https://github.com/username/projectname.git**

## Ignoring files and directories with a .gitignore file

how to avoid adding unwanted files (or file changes) in a Git repo. There are several ways
 (global or local .gitignore, .git/exclude) but keep in mind Git is managing content, which means: ignoring
actually ignores a folder content (i.e. files). An empty folder would be ignored by default, since it
cannot be added anyway.
You can make Git ignore certain files and directories — that is, exclude them from being tracked
by Git — by creating one or more **.gitignore files* in your repository.

When a file or directory is ignored, it will not be:

1. tracked by Git
2. reported by commands such as **git status* or **git diff*
3. staged with commands such as **git add -A*

Git keeps **"snapshots"** of the entire state of the project.
– Each checkin version of the overall code has a copy of
each file in it.
– Some files change on a given checkin, some do not.
– More redundancy, but faster.

![tracked-by-git](tracked-by-git.png)

In your local copy on git files can be
– In your local repo  (committed)

 Checked out and modified,
– but not yet committed (working copy)

In a "staging" area
– Staged files are ready to be committed.

**A commit saves a snapshot of all staged state.*

![local-operation](local-operation.png)


# Basic Git workflow

**Modify** files in your working directory.

**Stage** files, adding snapshots of them to your staging area.

**Commit** which takes the files in the staging area and stores that snapshot permanently to your Git directory.

![git-workflow](git-workflow.png)

**In Git** each user has their own copy of the repo, and commits changes to their local copy of the repo before pushing to the central server.
So Git generates a unique SHA-1 hash **(40 character string of hex digits)** for every commit.
– Refers to commits by this ID rather than a version number.


# Git Branch

A branch is a version of the repository that diverges from the main working project. It is a feature available in most modern version control systems. A Git project can have more than one branch. These branches are a pointer to a snapshot of your changes. When you want to add a new feature or fix a bug, you spawn a new branch to summarize your changes. So, it is complex to merge the unstable code with the main code base and also facilitates you to clean up your future history before merging with the main branch.

![git-branch](git-branch.png)


# The Operations that can be performed on a branch:**

Create Branch

Syntax:

**$ git branch  <branch name>**

List Branch

Syntax:

**$ git branch --list   or git branch**

Delete Branch

Syntax:

**$ git branch -d<branch name>**

