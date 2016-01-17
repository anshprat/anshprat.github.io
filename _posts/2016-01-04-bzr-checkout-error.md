---
layout: post
title: Bzr checkout error
---

I was trying to clone the [keystone package](https://code.launchpad.net/ubuntu/+source/keystone) using the given bzr command.

```bash
bzr branch lp:ubuntu/trusty/keystone`
```

However, I got the following error:

````
bzr: ERROR: Revision {package-import@ubuntu.com-20131016120940-8ite3zq710ktlx3c}
 not present in "Graph(StackedParentsProvider
    (bzrlib.repository._LazyListJoin(([CachingParentsProvider(CallableToParentsProviderAdapter(<bound method
  CHKInventoryRepository._get_parent_map_no_fallbacks of
  CHKInventoryRepository
  ('http://bazaar.launchpad.net/~ubuntu-branches/ubuntu/trusty/keystone/trusty/.bzr/repository/')>))], []))))".

````

A bit of googling lead me to [this bug](https://bugs.launchpad.net/bzr/+bug/888615)

which has a workaround..

```bash
bzr -Olaunchpad.packaging_verbosity=off branch lp:ubuntu/trusty/keystone
```

The above command worked flawlessly!

