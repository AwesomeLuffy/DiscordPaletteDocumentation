# DiscordMessageReader

# Input and Output

This processor don't have input. The output is a Message object.
```mermaid
flowchart LR
    processor[[DiscordMessageReader]] --> output([Message])
```


# Details

DiscordMessageReader is a Processor that extends SynchronousProcessor.

Due to the fact that we need a Bot Instance to read messages, we only can get this processor, from the class DiscordPalette.

Here is the code to get the processor:

```java
public class Main {
    public static void main(String[] args) {
    
        //First we get the DiscordPalette object by passing the JDA object to the getInstance method
        DiscordPalette discordPalette = DiscordPalette.getInstance(jdaBuilder);

        //Then we get the DiscordMessageReader object that represent the processor
        DiscordMessageReader discordMessageReader = (DiscordMessageReader) discordPalette.getDiscordMessageReader();
    }
}
```

> Actually you can get message from "two ways", the previous code is the first way, everytime the bot can read a message on Discord
> the processor will be called. The second way is similar but it's only when a message is "edited", to have this "processor" here the line :
> 
{style="note"}

```java
DiscordMessageReader discordMessageReader = (DiscordMessageReader) discordPalette.getDiscordMessageUpdateReader();
```

Instead of **getDiscordMessageReader()** we use **getDiscordMessageUpdateReader()**.