author: Kevin W. Gisi
company: ECRuby Meeting&mdash;April 8, 2010
title: Workflow With Git
subtitle:
footer: <a href='http://www.kevingisi.com'>Blog</a> | <a href='http://speakerrate.com/talks/2948-workflow-with-git'>SpeakerRate</a>
subfooter: Copyright &copy; 2010 by Kevin W. Gisi
code-theme: eiffel
code-line-numbers: false

# Summary

Regardless of what language you prefer, version-control is an essential tool for getting things done - especially when collaborating with others. Git, an open-source tool, has quickly become one of the most widely-used versioning systems, mainly thanks to the ability to branch and merge with relative ease. We'll take a look at how you can begin to integrate Git into your current workflow.

# Remember Windows 95?
<img src='http://upload.wikimedia.org/wikipedia/commons/3/3b/Windows_9X_BSOD.png'/>

# Archives
<img src='http://upload.wikimedia.org/wikipedia/commons/0/03/Rathaus_Koepenick_-_Safe.jpg'/>

# Diff
<pre>
*** /path/to/original ''timestamp''
--- /path/to/new      ''timestamp''
***************
*** 1,3 ****
--- 1,9 ----
+ This is an important
+ notice! It should
+ therefore be located at
+ the beginning of this
+ document!
...
</pre>

# Primitive Version Control
- Bitkeeper
- CVS
- Subversion

# Beginnings of Git
<img src='http://upload.wikimedia.org/wikipedia/commons/6/69/Linus_Torvalds.jpeg'/>

# Centralized Versioning
<img src='http://media.pragprog.com/titles/tsgit/images/repo-centralized2.png'/>

# Decentralized Versioning
<img src='http://media.pragprog.com/titles/tsgit/images/repo-distributed2.png'/>

# Git in Practice
<img src='http://media.pragprog.com/titles/tsgit/images/repo-shared-simple.png'/>

# Let's Create a Repository!
<pre>
:$> ls
about.html  contact.html  index.html  style.css

:$> git init
Initialized empty Git repository in /home/gisikw/project
</pre>

# Adding initial files
<pre>
:$> git add .

:$> git commit -m "Initial Commit"
Created initial commit ed3ec5b: Initial commit
 0 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 about.html
 create mode 100644 contact.html
 create mode 100644 index.html
 create mode 100644 style.css
</pre>

# Ignoring files
<pre>
:$> ls
about.html ~about.html contact.html index.html style.css test.html
</pre>

.gitignore
<pre>
~*.html
test.html
</pre>

# Git Revisions

Revision names:
- HEAD - the latest commit
- HEAD~ - the second-to-last-commit
- HEAD~2 - you get the idea

# Explicit Git Revisions
<pre>
:$> git log
commit 34c959355e37e188c6b842b37bb5ef453b068b69
Author: Kevin W. Gisi <=>
Date:   Thu Apr 8 04:23:15 2010 -0500

    Revert "Revert "Second add""
    
    This reverts commit ba6412405909e474f5bf99d4ce5829f1db5056f0.

commit ba6412405909e474f5bf99d4ce5829f1db5056f0
Author: Kevin W. Gisi <=>
Date:   Thu Apr 8 04:22:52 2010 -0500

    Revert "Second add"
    
    This reverts commit dadf5ec1bf8620b6765bb5beb58941d0b83978f6.
</pre>

# Reverting a Commit
<pre>
:$> git revert HEAD
</pre>
Create a new commit which undoes the changes most recently made.

# Tagging a Release
It's release time!
<pre>
:$> git tag 1.0
</pre>

Show current tags
<pre>
:$> git tag
1.0
</pre>

# Feature Branches

# Merging Branches

# Additional Resources

# Thanks!
