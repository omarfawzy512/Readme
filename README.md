**Software** **version** **control**

**Stefan** **Richter** **(DESY,** **MCnet)**

**Why** **version** **control?**

> Combine work of multiple collaborators Understand changes
>
> Support incremental development Compare and revert to earlier versions
> Backup
>
> Parallel versions
>
> Document development (for other developers and yourself, not for
> users)

**→** **version** **control** **is** **awesome.** **Use** **it** **all**
**the** **time.**

**What** **is** **Git?**

A distributed **version** **control** **system** (VCS) whose primary
user interface is the Unix command line. It basically keeps a
\"non-human-readable\" database of the ﬁles you put under version
control (\"track\") and provides commands to access and update that
database.

Graphical user interfaces, integration in Integrated Design
Environments, and **web** **platforms** **GitHub/GitLab/...** have
formed around the Git core software.

The aim here is not to tell you every single Git command in existence or
even to teach you all the functionality. The aim is to familiarise you
with the *principles* *of* *version* *control*, *some* *good*
*practices*, and *get* *you* *started* *on* *the* *practical* *matters*.

**Practical** **introduction** **by** **example**

We\'re going to walk you through an example. The things we show you here
will teach you all you need to know to collaborate on your team project
using Git.

**Setting** **up**

To initialise a new local repository do

> \>\>\> mkdir myrepo && cd myrepo \>\>\> git init

![](./pe0s14x3.png){width="0.6006944444444444in"
height="0.20052055993000875in"}Now try ls -a . Notice anything
interesting?

You can also clone existing repositories from a (usually remote)
different location. Git supports this via http(s), ssh, etc.

**We\'re** **going** **to** **create** **a** **remote** **repository**
**on** **GitLab** **and** **clone** **it.**

**Please** **create** **an** **account** **on** **GitLab**
**[[(http://gitlab.com](http://gitlab.com/))]{.underline}** **and**
**create** **a** **public** **repository** **called** **myrepo** **.**
Then clone it to your local machine by doing

> \>\>\> git clone https://gitlab.com/\<gitlab_username\>/myrepo.git
> \>\>\> cd myrepo

At this point you could set some conﬁgurations.

> \>\>\> git config core.editor \"emacs -nw\" \# or your favourite
> light-weight editor \>\>\> git config color.ui true \# makes life more
> fun
>
> \>\>\> git config \--list \# check that it worked!

To make settings for all repositories on your computer, add the ﬂag
\--global after git config .

You should also set your user name and email like this:

> \>\>\> git config user.name \"Stefan Richter\"
>
> \>\>\> git config user.email \"stefan.richter@example.com\"

These will be associated with your commits.

**Monitoring** **1**

Your ﬁrst best friend in Git is the command status :

> \>\>\> git status

It shows you the ﬁles in the repository, both tracked and untracked by
Git. Use this command all the time to know what\'s going on.

**Committing**![](./5xirctqp.png){width="7.418591426071741in"
height="4.282095363079615in"}

**Commit** **=** **saved** **snapshot** **of** **tracked** **ﬁles.** You
can always revert to a commit! You can also compare them, share them,
...

**Commits** **are** **cheap.** What do I mean by that?

![](./hcgipvsi.png){width="0.4114577865266842in"
height="0.20052055993000875in"}**Committing** **in** **Git** works in
two steps. First modiﬁed or untracked ﬁles are \"registered\" for the
next commit by using add . This is called *staging*. The *staged* ﬁles
are then committed with commit :

Image from https://git-scm.com
[([license]{.underline}](https://github.com/git/git-scm.com/blob/master/README.md#license))

Note: most other VCSs (e.g. Mercurial and SVN) don\'t have this two-step
structure. They don\'t have a staging area.

> \>\>\> git add \<path/to/file\> \# file is now staged for commit

![](./v5rrxv4y.png){width="0.422742782152231in"
height="0.20052055993000875in"}Note: in Mercurial and SVN, add is only
used to put a previously untracked ﬁle under version control. In Git, it
has a wider meaning!

> \>\>\> git commit

Then write a commit message. We\'ll give you hints for what is a good
message.

**Good** **commit** **messages** **matter!** [[Here are some good
recommendations]{.underline}](https://chris.beams.io/posts/git-commit)
(bedtime reading for you?).

Commits are identiﬁed by a unique hexadecimal number (a hash).

**Monitoring** **2**

Your second best friend is diff . It shows you changes (differences)
between versions. Without arguments, it shows all changes made to
tracked ﬁles in the repository since the last commit.

> \>\>\> git diff
>
> \>\>\> git diff \<path/to/file\>

( git diff can also be used to show differences between arbitrary
revisions. You can google it.)

Use

> \>\>\> git log

to see the commit history on your current branch. I use git log
-\<number\> a lot to only show the \<number\> last commits, e.g.

> \>\>\> git log -3

**A** **question** **and** **a** **suggestion:**

> What happens if you track ﬁles other than ﬂat text ﬁles?
>
> Create a hidden ﬁle .gitignore containing ﬁle patterns you want Git to
> ignore. These ﬁles won\'t show up in git status . E.g.
>
> \*.log \*.tmp test_data/
>
> my_personal_notes.txt

**Branches**

To check which branch you are on:

> \>\>\> git branch
>
> \>\>\> git branch -a

\# see where we are!

\# what\'s the difference?

Create a new branch:

> \>\>\> git branch dev1

Switch to the branch using

> \# dev1 is the name of the branch

![](./aqxensfn.png){width="0.8784722222222222in"
height="0.20052055993000875in"}checkout :

> \>\>\> git checkout dev1
>
> \>\>\> git branch \# see where we are!

To merge my changes into another branch (let\'s say, master ):

> \>\>\> git checkout master \>\>\> git merge dev1

**Working** **with** **remote** **repositories:** **sharing**

See what our remote is:

> \>\>\> git remote
>
> \>\>\> git remote -v

\# what\'s our remote

\# some more info

To update the local repository (*pull* changes):

> \>\>\> git pull

To update the remote repository (*push* changes):

> \>\>\> git push origin master

When pushing the ﬁrst time, do

> \>\>\> git push -u origin master \# -u tells the remote to track this
> branch in the fu

*A* *quick* *word* *on* *origin* *and* *master* *:* *these* *are* *the*
*default* *names* *of* *the* *remote* *repository* *and* *the*

*ﬁrst* *branch.* *They* *are* *not* *magical* *keywords* *and* *you*
*could* *use* *different* *names.* *However,* *don\'t.* *Unless* *you*
*have* *a* *good*
*reason.*![](./dllpgwcx.png){width="7.418591426071741in"
height="3.737100831146107in"}

A common workﬂow that your team could adopt:

Image from https://git-scm.com
[([license]{.underline}](https://github.com/git/git-scm.com/blob/master/README.md#license)).

*Personally* I like a model where every developer has one personal
development branch on the shared repository, named after them (e.g.
stefan in my case). (Everyone can have as many additional local branches
as they like, but they\'re not tracked in the shared repository.) People
push to their own branch, then request a merge into the
master/release/common development/whatever branch. At this point, the
others **review** **the** **code** **to** **be** **merged** for
correctness, understandability, maintainability, style & conventions,
robustness, resource effectiveness. When any necessary changes have been
made/commited/pushed, the merge request is accepted.

**Git\'s** **not** **perfect...**

Git is widely used and has many powerful features, but it also has some
annoying downsides. You might already have noticed that it\'s sometimes
quite unintuitive and difﬁcult to use...

**In** **fact,** **a** **tutorial** **like** **this** **glosses**
**over** **the** **total** **mess** **that** **you** **will** **from**
**time** **to** **time** **end** **up** **in** **with** **Git!**

[Here is a good post about problematic things in Git:
[https://stevebennett.me/2012/02/24/10-things-i-hate-about-git]{.underline}.
It is very instructive to read it! You will realise that sometimes it\'s
not you who\'s crazy, it\'s
Git.](https://stevebennett.me/2012/02/24/10-things-i-hate-about-git/)

![](./ut5ubirj.png){width="0.3116316710411199in"
height="0.1996522309711286in"}![](./whfv2ino.png){width="0.4114577865266842in"
height="0.1996522309711286in"}There are good **alternatives** to Git:
[[Mercurial]{.underline}](https://www.mercurial-scm.org/) ( hg ), which
is \"better\", and
[[Bazaar]{.underline}](https://en.wikipedia.org/wiki/GNU_Bazaar) ( bzr
), which I know nothing about.

SVN is an older central (i.e. not distributed) VCS and not as powerful
as Git and Mercurial. I don\'t use it
voluntarily.![](./e1e12h2r.png){width="5.6723851706036745in"
height="4.259850174978128in"}

**Finally**

![](./blbfb4su.png){width="1.0677077865266842in"
height="0.1996522309711286in"}No, Obama! **Never** **ever** **use**
**git** **rebase** **(or** **git** **cherry-pick** **)!** It rewrites
repository history and can even create loss of commited information.
[[Here\'s somebody who disagrees with
me.]{.underline}](https://nathanleclaire.com/blog/2014/09/14/dont-be-scared-of-git-rebase)
