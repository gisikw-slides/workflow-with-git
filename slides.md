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
- BitKeeper
- CVS
- Subversion

# Beginnings of Git
<img src='http://upload.wikimedia.org/wikipedia/commons/6/69/Linus_Torvalds.jpeg'/>
- Linus Torvalds
- 1.0 release on December 21, 2005
- Managed Linux kernel

# Centralized Versioning
<img src='http://media.pragprog.com/titles/tsgit/images/repo-centralized2.png'/>

# Decentralized Versioning
<img src='http://media.pragprog.com/titles/tsgit/images/repo-distributed2.png'/>

# Git in Practice
<img src='http://media.pragprog.com/titles/tsgit/images/repo-shared-simple.png'/>

# Let's Create a Repository!
<pre>
:$&gt; ls
about.html  contact.html  index.html  style.css

:$&gt; git init
Initialized empty Git repository in /home/gisikw/project
</pre>

# Adding initial files
<pre>
:$&gt; git add .

:$&gt; git commit -m "Initial Commit"
Created initial commit ed3ec5b: Initial commit
 0 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 about.html
 create mode 100644 contact.html
 create mode 100644 index.html
 create mode 100644 style.css
</pre>

# Git Add
Git add doesn't do what you think it does!
<pre>
:$&gt; echo "&lt;p&gt;Hello, world&lt;/p&gt;" &gt; index.html
:$&gt; git commit -m "Added initial text to index page"
# On branch master
# Changed but not updated:
#   (use "git add &lt;file&gt;..." to update what will be committed)
#
#       modified:   index.html
#
no changes added to commit (use "git add" and/or "git commit -a")
</pre>

# Git Add and Commit
Automatically add changes to files that are currently tracked:
<pre>
$:&gt; git commit -a -m "Added initial text to index page"
Created commit 94bc6d3: Added initial text to index page
 1 files changed, 1 insertions(+), 0 deletions(-)
</pre>

# Ignoring files
<pre>
:$&gt; ls
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
:$&gt; git log
commit fa8db86872c83fa62efa420548d8afe36bbb5fc6
Author: Kevin W. Gisi &lt;=&gt;
Date:   Thu Apr 8 04:35:06 2010 -0500

    Adjusted index to display standards-complient headers

commit c4e43f114f9c441ae20d51bf5277044d3edfca83
Author: Kevin W. Gisi &lt;=&gt;
Date:   Thu Apr 8 04:34:26 2010 -0500

    Added help.html file to display usage and FAQ information
</pre>

# Reverting a Commit
<pre>
:$&gt; git revert HEAD
</pre>
Create a new commit which undoes the changes most recently made.

# Tagging a Release
It's release time!
<pre>
:$&gt; git tag 1.0
</pre>

Show current tags
<pre>
:$&gt; git tag
1.0
</pre>

# Feature Branches

# Merging Branches

# Additional Resources
<img src='http://assets1.pragprog.com/images/covers/190x228/tsgit.jpg?1236205329'>
- Pragmatic Version Control Using Git
- Travis Swicegood

# Thanks!
