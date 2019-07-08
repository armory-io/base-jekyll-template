---
date: 2018-11-20
title:  Armory Halyard Upgrade
categories:
   - Admin
description:  Armory Halyard Upgrade
type: Document
---

### Question:

If I'm using Armory Spinnaker, how do I upgrade?

***

### Answer:

First, determine which version of Armory Spinnaker you want to use.  You can get this list by running `hal version list`:

```bash
$ hal version list
+ Get current deployment
  Success
+ Get Spinnaker version
  Success
+ Get released versions
  Success
+ You are on version "1.14.209", and the following are available:
 - 1.14.209 (OSS Spinnaker v1.8.6):
   Changelog: https://docs.armory.io/release-notes/armoryspinnaker_v1.14.209/
   Published: Thu Sep 13 18:42:49 EDT 2018
   (Requires Halyard >= 1.0.0)
 - 2.0.0 (OSS Release 1.9.5):
   Changelog: https://docs.armory.io/release-notes/armoryspinnaker_v2.0.0/
   Published: Fri Nov 02 19:42:47 EDT 2018
   (Requires Halyard >= 1.2.0)

```

Once you know what version you want to upgrade (or downgrade) to, update your halconfig with `hal config version edit --version [VERSION]`:

```bash
$ hal config version edit --version 2.0.0
+ Get current deployment
  Success
+ Edit Spinnaker version
  Success
+ Spinnaker has been configured to update/install version
  "2.0.0". Deploy this version of Spinnaker with `hal deploy apply`.
```

Then, apply your upgrade with `hal deploy apply`