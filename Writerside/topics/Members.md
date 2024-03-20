# Members

> The difference between a Member and a User is that a Member is a User that is in a Guild.
{style="note"}


> Each processor is a class that extends UnaryFunction so the use will be the same for all of them.

## Id

```mermaid
    flowchart LR
      input1([Member]) --> processor[[Members.id]] --> output1([String])
```

## Nickname

```mermaid
    flowchart LR
      input1([Member]) --> processor[[Members.nickname]] --> output1([String])
```

## User

```mermaid
    flowchart LR
      input1([Member]) --> processor[[Members.user]] --> output1([User])
```

## Guild

```mermaid
    flowchart LR
      input1([Member]) --> processor[[Members.guild]] --> output1([Guild])
```

## Avatar URL

> Due to a Discord Update, member can have a different avatar per guild, so the processor will return the avatar of the member in the guild.

```mermaid
        flowchart LR
        input1([Member]) --> processor[[Members.avatarUrl]] --> output1([String])
```

## Roles

```mermaid
        flowchart LR
            input1([Member]) --> processor[[Members.roles]] --> output1([Collection<Role>])
```

## TimeJoined

```mermaid
        flowchart LR
            input1([Member]) --> processor[[Members.timeJoined]] --> output1([Long])
```

## IsGuildOwner

```mermaid
        flowchart LR
            input1([Member]) --> processor[[Members.isGuildOwner]] --> output1([Boolean])
```
   
