---
layout: post
title: How to rebase
---

As a follow up to the easy rebase post [[http://anshprat.github.io/easy-git-rebase/]], the need for the actual rebase came up recently.
The usecase is -

when doing a upstream merge and creating a PR with a single new commit, the PR ended up showing some other commits from master.
These needed to be rebased.

So, here is what Dan told me about (though in some other context/usecase) -

** How to rebase?

```bash

git fetch origin
git rebase origin/master
# git rebase --continue as required to fix merge conflicts
# git push --force as your will have to rewrite history when you finish
```

