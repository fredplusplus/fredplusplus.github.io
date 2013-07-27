---
layout: post
title: "Newbie's Git Cheatsheet"
description: ""
category: Geek
tags: [Git]
---
{% include JB/setup %}

My team is switching our entire code base from perforce to git. And so far I gotta say git roks.

Here is my notes of some really simple and day-to-day commands:

### Basic Commands
{% highlight java linenos%}
	git status
	git add (filename)
	git commit 
	git diff --staged
	git pull
	git log --graph --all
{% endhighlight%}
### Updating one file
{% highlight java linenos %}
	git add (file)
	git commit
	git push
{% endhighlight%}
### Integrating with remote
{% highlight java linenos %}
	git pull
{% endhighlight%}
or
{% highlight java linenos %}
	git fetch
	git merge
{% endhighlight%}
### revert a file that's not committed
{% highlight java linenos %}
	git reset HEAD -- (filename)
{% endhighlight%}

### revert a file that's commited
First figure out which version should it be reverted to: 
{% highlight java linenos %}
	git log --graph --all
{% endhighlight%}
Copy the sha1 from the desired history
{% highlight java linenos %}
	git checkout (sha1) (filename)
{% endhighlight%}
### Work on 2 branches at the same time
Find a point where you want to create branch: 
{% highlight java linenos %}
	git log --graph --all
{% endhighlight%}

Go to that point: 
{% highlight java linenos %}
	git checkout (sha1)
{% endhighlight%}

create 2 branches: 
{% highlight java linenos %}
	git branch b1
	git branch b2
{% endhighlight%}
switch to one of them and work on it:
{% highlight java linenos %}
	git checkout (branchname)
{% endhighlight%}
Merge branch back to mainline:
{% highlight java linenos %}
	git checkout master
	git merge b1
	git merge b2
	git commit
	git push
{% endhighlight%}