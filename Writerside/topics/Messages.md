# Messages

## Details

> Each processor is a class that extends UnaryFunction so the use will be the same for all of them.

### Id

1. Graph

    ```mermaid
    flowchart LR
      input1([Message]) --> processor[[Messages.id]] --> output1([String])
    ```

### Content

1. Graph

    ```mermaid
    flowchart LR
      input1([Message]) --> processor[[Messages.content]] --> output1([String])
    ```

#### Author

1. Graph

    ```mermaid
    flowchart LR
        input1([Message]) --> processor[[Messages.author]] --> output1([User])
    ```

#### GuildMember

1. Graph

    ```mermaid
    flowchart LR
        input1([Message]) --> processor[[Messages.member]] --> output1([Member])
    ```
   
2. Code
   
#### Channel

1. Graph

    ```mermaid
    flowchart LR
        input1([Message]) --> processor[[Messages.channel]] --> output1([Channel])
    ```
   
#### Guild

1. Graph

    ```mermaid
    flowchart LR
        input1([Message]) --> processor[[Messages.guild]] --> output1([Guild])
    ```
   
#### Files

1. Graph

    ```mermaid
    flowchart LR
        input1([Message]) --> processor[[Messages.files]] --> output1([List<File>])
    ```

... and so on.

