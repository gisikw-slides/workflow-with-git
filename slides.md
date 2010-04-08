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
<div class="handout">
Regardless of your choice in programming language, computer errors are bound to happen. This is precisely why we need to have a way to back up our files. However, there's also an immense benefit to having a way of storing changes in files over time.
</div>
<img src='http://upload.wikimedia.org/wikipedia/commons/3/3b/Windows_9X_BSOD.png'/>

# Archives
<div class="handout">
One way to manage this need is to simply take a snapshot of the project at various times, and store these on some backup device. A primitive method, it is nonetheless still often used. Individuals can simply zip, or tar up their project directories, throw a version number on it, and lock it away. This mechanism starts to break down with multiple collaborators, because it becomes nearly impossible to determine what version you're working with. It's also terribly inefficient, as far as data storage goes.
</div>
<img src='http://upload.wikimedia.org/wikipedia/commons/0/03/Rathaus_Koepenick_-_Safe.jpg'/>
* Compressed files
* Version stamps: rel_1.0.3.2554beta.tar.gz
* Locked away
* Becomes challenging with multiple contributors

# Diff
<div class="handout">
A space-saving alternative to storing a new version for each file, is to simply store the changes. The GNU "diff" tool provides a means of recording the differences between two files, and even write a new file that simply holds the changes. This new file can then be sent to collaborators, who can apply it to their current version. The issue of determining order of diffs is still an issue, but at the very least, storage is now reduced to maintaining the <em>changes</em> in a file, rather than the entire file itself.
</div>
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
<div class="handout">
In order to automate the process, there are a few things that would be necessary in software designed to manage versions.
</div>
Goals of Versioning Software
- Track changes over time
- Handle human concurrency issues
- Assist in merge conflicts
Examples
- BitKeeper, CVS, Subversion

# Beginnings of Git
<img src='http://upload.wikimedia.org/wikipedia/commons/6/69/Linus_Torvalds.jpeg'/>
- Created by Linus Torvalds
- Tried to avoid conventional practices (CVS,BitKeeper)
- 1.0 release on December 21, 2005
- Used to Manage Linux kernel

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
<pre>
:$&gt; git branch html5
:$&gt; git checkout html5
Switched to branch "html5"
:$&gt; git mv index.html start.html
:$&gt; git commit -am "Moved index.html to start.html"
Created commit 9c56488: Moved index.html to start.html
 1 files changed, 0 insertions(+), 0 deletions(-)
 rename index.html =&gt; start.html (100%)
</pre>

# Master Stays Untouched
<pre>
:$&gt; git checkout master
Switched to branch "master"
:$&gt; ls
about.html  contact.html  help.html  index.html  style.css
</pre>

# Merging Branches
Navigate to the branch you want to work on
<pre>
:$&gt; git merge html5
</pre>

Merge the other branch into the current branch.

# Remote Repositories

Often, we want to push our commits to another repository. We need to register the repository first.
<pre>
:$&gt; git remote add origin git@github.com:gisikw/samply-application.git
</pre>
We tell Git a local name to call the remote, and the url where it can be accessed.

# Pushing and Pulling from Remotes

Push any new commits in our master branch to the remote origin
<pre>
:$&gt; git push origin master
</pre>

Pull any new commits on the remote origin into our master branch
<pre>
:$&gt; git pull origin master
</pre>

# Additional Resources
<img src='http://pragprog.com/images/covers/original/tsgit.jpg'>
- <a href='http://pragprog.com/titles/tsgit/pragmatic-version-control-using-git'>Pragmatic Version Control Using Git</a> by Travis Swicegood
- <a href='http://help.github.com'>http://help.github.com</a>
- <a href='http://www.gitcasts.com/'>GitCasts</a>

# Thanks!

Kevin W. Gisi

&lt;<a href='mailto:kevin@kevingisi.com'>kevin@kevingisi.com</a>&gt;
