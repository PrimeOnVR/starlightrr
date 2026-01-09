---
description: About the Noxis Dictionary search tool.
icon: magnifying-glass
---

# Search for keys in ROM/External

The [noxis-dictionary.md](../low-level/noxis-dictionary.md "mention") search tool allows you to easily search dictionaries in Noxis throughout various parts of it. It simplifies key searching into a simple chip, allowing for better code overall.

<figure><img src="../../../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

To use it, you must enter two things, which is the **keys you are searching for**, and the **search target**.&#x20;

The **keys you are searching for** is a key (or keys, concatenated with `` ` `` ,) and the **search target** is either:

* A hostname of a service, in which the chip will pull from the service's [rom.md](../low-level/rom.md "mention")
* An external search target, which is a ROM or [#options](../noxis-parts/noxis-communicator.md#options "mention") portion of a Communication
* The Rec Room Object of a service, in which it will also pull from the service's [rom.md](../low-level/rom.md "mention")

After that, it will output **Resulting Value(s)**, which is your key's value (or values, concatenated with `` ` `` , in the same order as your keys.)
