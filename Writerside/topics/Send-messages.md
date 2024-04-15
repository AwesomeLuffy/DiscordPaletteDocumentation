# Send messages

> The following example show an example to how to send messages in a Discord channel.

## Demo

![DemoSendMessage](DiscordPalette_SendMessage.gif)

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

        // First we need to get a channel to send a message
        // In this example, we will take the one where the messages were read
        ApplyFunction getChannel = new ApplyFunction(Messages.channel);

        // We will prepare a text to send when someone send message
        TurnInto turnIntoMyTest = new TurnInto("Hey ! I saw your message !");

        // We need a fork to trigger the TurnInto
        Fork forkedInput = new Fork(2);

        // Then we get the processor to send a message
        // This processor has 2 input
        // 1 - The channel where the message will be sent
        // 2 - The message to send
        // This processor return the Message object that the bot sent
        SynchronousProcessor messageSender = MessageChannels.sendMsg;

        // We create a print object to show in the Console what the bot sent
        Print print = new Print();

        // Finally we connect our processors

        Connector.connect(reader, 0, forkedInput, 0);

        Connector.connect(forkedInput, 0, getChannel, 0);
        Connector.connect(forkedInput, 1, turnIntoMyTest, 0);

        Connector.connect(getChannel, 0, messageSender, 0);
        Connector.connect(turnIntoMyTest, 0, messageSender, 1);

        Connector.connect(messageSender, 0, print, 0);

    }
```