# Guilds

> Some of the processors extends BinaryFunction, this means that the processor needs two inputs to work.

## Id

```mermaid
    flowchart LR
      input1([Guild]) --> processor[[Guilds.id]] --> output1([String])
```

## Name

```mermaid
    flowchart LR
      input1([Guild]) --> processor[[Guilds.name]] --> output1([String])
```

## MemberCount

```mermaid
    flowchart LR
      input1([Guild]) --> processor[[Guilds.memberCount]] --> output1([Integer])
```

## Icon URL

```mermaid
        flowchart LR
        input1([Guild]) --> processor[[Guilds.iconUrl]] --> output1([String])
```

## Owner

```mermaid
        flowchart LR
        input1([Guild]) --> processor[[Guilds.owner]] --> output1([Member])
```

## Description

```mermaid
        flowchart LR
        input1([Guild]) --> processor[[Guilds.description]] --> output1([String])
```

## Members

```mermaid
        flowchart LR
            input1([Guild]) --> processor[[Guilds.members]] --> output1([Collection<Member>])
```

## Roles

```mermaid
        flowchart LR
            input1([Guild]) --> processor[[Guilds.roles]] --> output1([Collection<Role>])
```

## MemberFromUser

```mermaid
        flowchart LR
            input1([Guild])
            input2([User]) 
            processor[[Guilds.memberFromUser]]
            output1([Member])
            input1 --> processor
            input2 --> processor
            processor --> output1
```

## MemberFromId

```mermaid

        flowchart LR
            input1([Guild])
            input2([String]) 
            processor[[Guilds.memberFromId]]
            output1([Member])
            input1 --> processor
            input2 --> processor
            processor --> output1
```

