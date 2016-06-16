---
layout: post
title: How to manage conflict during git rebase?
---

In this blogpost, I am going to tell you why I use rebase and how I resolve git conflicts not related to my code change while doing a rebase.

I like to work under fork->branch->PR model instead of clone->branch->PR model.
(i.e, I work on the clone of my fork instead of clone of upstream, in this case upstream being our team's main repo).

The way I keep my fork updated with upstream is a simple git rebase using my [gr](https://github.com/anshprat/myFiles/blob/master/bin/gr) script. (The g in the above script is not an alias to git directly but rather [another script](https://github.com/anshprat/myFiles/blob/master/bin/g) that I use for managing my git commands. The reason for using this instead of aliases is that this is easily expandable to new git commands without having to add new alias for everything!)
The reason I use git rebase instead of git merge is to avoid the pesky "Merge" commits. Infact, even if I somehow end with a commit message during some other pull command (I have multiple copies of my repos presently, due to changes in our workflow over last few weeks), I remove the merge commit using a rebase thereafter.

Sometimes, if the branch is pretty outdated, you may run into a git conflict while doing a git rebase. Now resolving conflicts on large numbers of files is always a problem - all the more so when those changes are not related to your change at all! 

My workflow is such that my forks master has no changes other than the upstream master changes. So I keep my master as source of truth in sync with upstream master. All rebases in other branches of my fork happen against my master.

So, keeping the above in mind, my way of resolving non-related conflicts is:

- Ensure your changes are all committed to your branch (hopefully in one or as few commits as possible). If you have multiple commits, you may want to squash them using [git reset](http://hackalyst.info/easy-git-rebase/) or [rebase](http://hackalyst.info/real-rebase/)
- Ensure your master is updated to latest upstream state.
- Create a new branch from your master
- Cherry-pick your changes from the branch in step 1 above to your new branch created in last step.

And voila! Now you have a branch with all your changes on top of the latest upstream master!

So we saw here, how do I use a new git branch to get out of tricky git rebase conflict resolutions and how you can do the same!

