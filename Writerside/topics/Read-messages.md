# Read messages

> The following example show in details how to get the read the messages from Discord and get it in a BeepBeep project.


## Demo

![DemoReadMessage](DiscordPalette_ReadMessage.gif)

## Code

```java
    public static void main(String[] args) {
        // The token is the key to connect to the Discord API
        String token = "YOUR_TOKEN_HERE";

        // Create a new JDA object (it's the instance of our bot)
        JDA discordBot = JDABuilder.createDefault(token)
                .enableIntents(GatewayIntent.MESSAGE_CONTENT)
                .build();

        // Create a new DiscordPalette object to interact with BeepBeep
        DiscordPalette palette = DiscordPalette.getInstance(discordBot);

        // Then get the processor to read messages
        Processor reader = palette.getDiscordMessageReader();

        // We get a function processor to only get the content of the message
        ApplyFunction getMessageContentFunction = new ApplyFunction(Messages.content);

        // Now we simply create a Print processor to show the messages from Discord
        Print print = new Print();

        // Connect the reader to the getMessageContentFunction
        Connector.connect(reader, getMessageContentFunction);

        // Connect the getMessageContentFunction to the print processor
        Connector.connect(getMessageContentFunction, print);
    }
```
