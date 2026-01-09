---
description: What the Noxis Communicator is, and what it does
icon: comments-question-check
---

# Noxis Communicator

The Noxis Communicator is what connects isolated versions of Noxis to one another. This page attempts to help you learn more about its inner workings, in an easy and quick manner.

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Why Communicator runs on a Studio Object

The Noxis Communicator is one of, if not the most important and complex part of Noxis. So much so, in fact, that we have written abstraction layers to make it easier to work with. This is because of the goal that the Communicator is trying to solve. You see, as Noxis is designed to come packaged in multiple parts, spread across multiple inventions, we needed a protocol to be able to communicate between those inventions. This led to trying out several, built in ways of wireless CV2 in Rec Room, all with their own drawbacks. Here is why each one didn't work for us:

* ❌ Event Senders: Does not connect between inventions
* ❌ Normal CV2 wires: Requires the user to connect stuff together, and isn't robust
* ❌ Message Senders: Only in beta, and only supports one event per game frame
* ❌ Object Properties: Only in beta
* ❌ Text: 512 character limit

Because of the drawbacks of each one, we ended up coming up with our own solution, which ended up to be:

* ✔️ Custom Studio Object w/Text get and set function: Works in every room version

With our own custom studio object, and the recent addition of making studio objects into inventions in R1, this was, and still is, the best solution to run Noxis Communicator on.



## Communication Formatting

The raw Noxis communication protocol is split into two parts, divided by the `˭` character. Those two parts are the [#options](noxis-communicator.md#options "mention") and the [#data](noxis-communicator.md#data "mention") portion.

```
sending˽[SENDING SERVICE]˸receiving˽[RECEIVING SERVICE]˸command˽[COMMAND]˭[DATA]
```

### Options

The options portion houses several parts, and is Dictionary based (keys corresponding to values) with those parts being:

* The `sending` key, which is the service hostname that is sending a communication,
* The `receiving` key, which is the server hostname that is receiving a communication,
* The `command` key, which is the command to be run on the receiving service.

Apps are recommended to use the [#data](noxis-communicator.md#data "mention") portion to hold data, however, if interfacing directly with the Communicator without any abstraction layers, you can add your own keys to make and read from using the [search-for-keys-in-rom-external.md](../noxis-tools/search-for-keys-in-rom-external.md "mention") tool. In addition, if you prefer to not use any tools, you can learn about how Noxis's key system works at the [noxis-dictionary.md](../low-level/noxis-dictionary.md "mention") page.

### Data

Data is quite a simple feature, as it is simply outputted for the service to use, whenever a communication is sent to it. It can be whatever the service wants, and as such, doesn't have any specific formatting standards.

### Other Features

If interfacing directly with the Communicator, you are able to send multiple communications by concatenating them with the `˲` character.
