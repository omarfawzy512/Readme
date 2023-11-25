## What is Git

Git is a free, distributed version control system which allows programmers to keep track of code
changes, via "snapshots" (commits), in its current state. Utilizing commits allows programmers to
test, debug, and create new features collaboratively. All commits are kept in what is known as a
"Git Repository" that can be hosted on your computer, private servers, or open source websites,
such at Github.
Git also allows for users to create new "branches" of the code, which allows different versions of
the code to live alongside each other.

## Git has 3 different "areas" for your code:

• Working directory: The area that you will be doing all of your work in (creating, editing,
deleting, and organizing files)

• Staging area: The area where you will list the changes that you have made to the working
directory

• Repository: Where Git permanently stores the changes you have made as different
versions of the project

## Create your first repository, then add and commit files
At the command line, first verify that you have Git installed:
On all operating systems:

 **git --version**  

 On UNIX-like operating systems:
 
  **which git**
  
After installing Git, configure your username and email address as below . Do this before making a commit.
– git config --global user.name "Bugs Bunny"
– git config --global user.email bugs@gmail.com
Once Git is installed, navigate to the directory you want to place under version control and create
an empty Git repository:

**git init**

This creates a hidden folder, .git, which contains the plumbing needed for Git to work.
Next, check what files Git will add to your new repository; this step is worth special care:

**git status**
