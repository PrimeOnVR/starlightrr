---
description: How Noxis Dictionaries work.
icon: key
---

# Noxis Dictionary

Noxis dictionaries are found in several places, such as the [rom.md](rom.md "mention") and [queued-communications.md](queued-communications.md "mention"). They can be searched via the [search-for-keys-in-rom-external.md](../noxis-tools/search-for-keys-in-rom-external.md "mention") tool, and are a low-level way to get data in a robust way.

```
key˽value
```

They are formatted with a key and a value, split by the `˽` character.



## Why dictionaries?

Dictionaries exist to solve a specific problem to do with lists. Normal lists, which is what Noxis technically uses under the hood (just with a lot of extra tweaking to make them act as Dictionaries,) have a problem known as **List Offsetting**. Basically, normally, to get values in a list, you specify the index of that element in the list. This is great for most things, but issues arise when you end up changing the list.

```
0 - "This is some data!"
1 - "This is more data!"
2 - "This is some important data!"
```

Due to Noxis being very interconnected, and each developer possibly adding their own elements to the list, those values can be tampered with. For example, if a developer were to add some data of their own to the first element, this may happen:

```
0 - "Custom Dev Text"
1 - "This is some data!"
2 - "This is more data!"
3 - "This is some important data!"
```

All of the original data is offset! Trying to get a value you are looking for will result in the wrong data!

But, you may ask, why would a developer ever do something like this, when they could just append to the end of the list? Well, you also have to take into account something more complicated: **Noxis Updates**. Over time, the Noxis Team may update Noxis to add more functionalities, like adding more pieces of data to the [rom.md](rom.md "mention"), [queued-communications.md](queued-communications.md "mention"), or other lists that Noxis uses. This means, as a developer, if you were to use the same things that we do, your services could be confused with the list offsetting, or Noxis could try and read your custom data as official functions. That causes breakages! and in the end, is why we had to end up using our complicated, albeit slower, dictionary system.
