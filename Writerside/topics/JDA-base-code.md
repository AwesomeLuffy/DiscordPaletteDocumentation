# JDA base code

Here the code for the base of your bot and start it.

```java
public class Main {

    private static final String token = "PLACE_YOUR_TOKEN";
    
    public static void main(String[] args) {
        JDA jdaBuilder = JDABuilder.createDefault(Main.token)
                .setActivity(Activity.watching("Playing with Lego"))
                .enableIntents(GatewayIntent.MESSAGE_CONTENT)
                .build();
    }
}
```

Don't worry we will explain this few lines !\

| Keyword                                       | Explanation                                                                       |
|-----------------------------------------------|-----------------------------------------------------------------------------------|
| JDA builder = JDABuilder...                   | It will represent our discord bot object.                                         |
| .createDefault(Main.Token)                    | We simply send to the library our token that we get on Discord Developer Portal   |
| .setActivity                                  | It's optional line, just to show what the bot doing on Discord on the member list |
| .enableIntents(GatewayIntent.MESSAGE_CONTENT) | Important line, it will allow us to read the content of the messages              |
| .build()                                      | Return us the Bot object after defined all we want inside.                        |

Now if you launch your program you have a bot that is connected to Discord.

> It's not an introduction to JDA and how to code a whole Discord bot, this is just the base code to start your bot. And use BeepBeep.\
> If you want further information about JDA, you can go to the [JDA wiki](https://jda.wiki/introduction/jda/)
> 
{style="warning"}
