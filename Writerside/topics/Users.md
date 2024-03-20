# Users

> The difference between a Member and a User is that a Member is a User that is in a Guild.
{style="note"}


> Each processor is a class that extends UnaryFunction so the use will be the same for all of them.

## Id

```mermaid
    flowchart LR
      input1([User]) --> processor[[Users.id]] --> output1([String])
```

## Name

```mermaid
    flowchart LR
      input1([User]) --> processor[[Users.name]] --> output1([String])
```

## Avatar URL

> Due to a Discord Update, user can have a different avatar per guild, so the processor will return the default avatar of the user.

```mermaid
        flowchart LR
        input1([User]) --> processor[[Users.avatarUrl]] --> output1([String])
```


