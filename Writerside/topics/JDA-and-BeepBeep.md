# JDA and BeepBeep

Now that you have a bot connected to Discord, we will see how to use DiscordPalette to interact with Discord and
BeepBeep.\

## First we will add some lines to our base code

```java
public class Main {

    private static final String token = "PLACE_YOUR_TOKEN";
    
    public static void main(String[] args) {
        JDA jdaBuilder = JDABuilder.createDefault(Main.token)
                .setActivity(Activity.watching("Playing with Lego"))
                .enableIntents(GatewayIntent.MESSAGE_CONTENT)
                .build();
                
        DiscordPalette discordPalette = DiscordPalette.getInstance(jdaBuilder);
        
        DiscordMessageReader discordMessageReader = (DiscordMessageReader) discordPalette.getDiscordMessageReader();        
    }
}
```

<procedure title="Explanation of the code">
<step>
    <p>First we create a new instance of DiscordPalette with the JDA object</p>
    <code-block lang="java">
    DiscordPalette discordPalette = DiscordPalette.getInstance(jdaBuilder);
    </code-block>
    DiscordPalette can handle multiple instances of a bot, so we simply pass our object to it.
</step>
<step>
    <p>Then we get the DiscordMessageReader from the DiscordPalette</p>
    <code-block lang="java">
    DiscordMessageReader discordMessageReader = (DiscordMessageReader) discordPalette.getDiscordMessageReader();
    </code-block>
    It's a way to read the messages from Discord and pass it to BeepBeep, <strong>DiscordMessageReader</strong> is a <strong>BeepBeep Processor</strong>.
</step>
</procedure>

Now to see if everything we work, we need to test it.\

Add this line at the end of your main method:

```java
        ApplyFunction getMessageContent = new ApplyFunction(Messages.content);
        Print print = new Print();
        
        Connector.connect(discordMessageReader, getMessageContent);
        Connector.connect(getMessageContent, print);
```

> Don't worry if you don't know what is "ApplyFunction" and "Messages.content", all will be explained later.
>
{style="note"}

Now if you run your program, you should see the content of the messages in your console.

