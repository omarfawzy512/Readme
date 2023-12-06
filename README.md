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

## Syncing (git remote)

**Git Fetch**

The git fetch command downloads commits, files, and refs from a remote repository into your local repo. Fetching is what you do when you want to see what everybody
When downloading content from a remote repo, git pull and git fetch commands are available to accomplish the task. You can consider git fetch the 'safe' version of the two commands. It will download the remote content but not update your local repo's it will download the remote content for the active local branch and immediately execute **git merge** to create a merge commit for the new remote content

**git fetch <remote>**
above command Fetch all of the branches from the repository. This also downloads all of the required commits and files from the other repository.

**git fetch <remote> <branch>**
Same as the above command, but only fetch the specified branch.

**git fetch --all**
A power move which fetches all registered remotes and their branches:












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

