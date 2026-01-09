---
description: How Noxis's Prerequisites system works.
icon: list-check
---

# Noxis Prerequisites

Noxis Prerequisites is like a checklist that Noxis automatically checks before your service starts. Currently, it only supports service dependencies, but this may change in the future.&#x20;

<figure><img src="../../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

With Prerequisites, you can input dependencies (Standards defined in [tagging.md](../low-level/tagging.md "mention")) and it will automatically check if those groups or services exist before running any of your services.

After checking if all Prerequisites has been met, if any dependencies have been missed, data will be passed over to [noxis-developer-info.md](noxis-developer-info.md "mention") to throw an error to get the user's attention.
