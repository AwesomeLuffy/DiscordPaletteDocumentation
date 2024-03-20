# MessageChannels

> Some processor inside this topic is particlar and will be explained in the processor section.

## Id

```mermaid
    flowchart LR
      input1([MessageChannel]) --> processor[[MessageChannels.id]] --> output1([String])
```

## Name

```mermaid
    flowchart LR
      input1([MessageChannel]) --> processor[[MessageChannels.name]] --> output1([String])
```

## Guild

```mermaid
    flowchart LR
      input1([MessageChannel]) --> processor[[MessageChannels.guild]] --> output1([Guild])
```

## CanTalk

Output a boolean that indicates if the bot can send messages to the channel.

```mermaid
    flowchart LR
      input1([MessageChannel]) --> processor[[MessageChannels.canTalk]] --> output1([Boolean])
```

## SendMessage

> This processor is particular, it can perform an action and the actual way to send message on Discord from DiscordPalette.

```mermaid
    flowchart LR
      input1([MessageChannel])
      input2([String])
      processor[[MessageChannels.sendMessage]]
      output1([Message])
      input1 --> processor
      input2 --> processor
      processor --> output1
```

`MessageChannel` is the channel where the message will be sent\
`String` is the content of the message\
`Message` is the "return" of the Message just sended so you can use it to perform other actions.

> If the message can't be sent due to an error (RateLimited, InsufficientPermission, etc...) the processor will return nothing.
{style="warning"}