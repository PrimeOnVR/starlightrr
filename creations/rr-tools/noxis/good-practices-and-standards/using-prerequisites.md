---
description: How to use Noxis Prerequisites properly.
icon: clipboard-list-check
---

# Using Prerequisites

When using [noxis-prerequisites.md](../noxis-parts/noxis-prerequisites.md "mention"), there are a few things you should do to keep a standard on your service. Some of those standards are:

* Always require `nsSystem` , to keep your service running smoothly
* Require everything you use, to prevent breakages
* Make every event you have (eg: update, update 30hz, ect) only work if Prerequisites says that they should run

Also, make sure to look at [command-and-tagging-standards.md](command-and-tagging-standards.md "mention") to see about how you should write your tags in the first place.
