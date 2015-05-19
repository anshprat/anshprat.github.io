---
layout: post
title: Easy git rebase using reset
---

I have tried my hands at git rebase a couple of times at Aerospike and Reliance. However I never was able to get it done nicely.
Almost always, the requirement is to squash the intermediate git commit messages while retaining the actual work done.

For example, from:

```bash

commit 1 - This should work
commit 2 - oops, fixed
commit 3 - really fixed it now!
commit 4 - minor typo
```

to:

```bash
commit 1 - This should work
commit 2 - working final
```

I was suggested one easy way by [Dan Bode](https://github.com/bodepd) in [this comment](https://github.com/JioCloud/puppet-rjil/pull/584#discussion_r29730271) and this way almost always works.
(I am yet to come across a way when it would fail but maybe coz I am no longer doing merges inbetween of the commits)

Here is the suggestion provided by Dan:

```bash
git log # to find the commit before where you start
git reset <that_commit>
git add; git commit # recommit your code as a new commit
git push --force # force push that commit to this branch
```

the other option is to do a interactive rebase using git rebase -i and squash all the commits to a single commit

Maybe I was not doing the rebase correctly (yeah I almost always squashed everything and ended with conflicts and the conflicts resolutin took me back to old state or divergence).

Till I figure out how to do rebase correctly (if I really need that again), the above is good enough for my usecase.
{{ page.conten | markdownify }}
