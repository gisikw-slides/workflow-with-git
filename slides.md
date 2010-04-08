author: Kevin W. Gisi
company: ECRuby Meeting&mdash;April 8, 2010
title: Workflow With Git
subtitle:
footer: <a href='http://speakerrate.com/talks/2948-workflow-with-git'>SpeakerRate</a>
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
+
  This part of the
  document has stayed the
  same from version to
***************
*** 5,20 ****
  be shown if it doesn't
  change.  Otherwise, that
  would not be helping to
! compress the size of the
! changes.
!
! This paragraph contains
! text that is outdated.
! It will be deleted in the
! near future.
 
  It is important to spell
! check this dokument. On
  the other hand, a
  misspelled word isn't
  the end of the world.
--- 11,20 ----
  be shown if it doesn't
  change.  Otherwise, that
  would not be helping to
! compress anything.
 
  It is important to spell
! check this document. On
  the other hand, a
  misspelled word isn't
  the end of the world.
***************
*** 22,24 ****
--- 22,28 ----
  this paragraph needs to
  be changed. Things can
  be added after it.
+
+ This paragraph contains
+ important new additions
+ to this document.
</pre>

# Primitive Version Control
-Bitkeeper
-CVS
-Subversion

# Beginnings of Git
<img src='http://upload.wikimedia.org/wikipedia/commons/6/69/Linus_Torvalds.jpeg'/>

# Centralized Versioning

# Distributed Versioning

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
