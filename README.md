# Telegram Bot Java Library
[![Telegram](/TelegramBots.svg)](https://telegram.me/JavaBotsApi)


A simple to use library to create Telegram Bots in Java which also called OOPS

## Contributions
Feel free to fork this project, work on it and then make a pull request against **DEV** branch. Most of the times I will accept them if they add something valuable to the code.

Please, **DO NOT PUSH ANY TOKEN OR API KEY**, I will never accept a pull request with that content.

## Webhooks vs GetUpdates
Both ways are supported, but I recommend long polling method.

## Usage

Just import add the library to your project with one of these options:

  1. Using Maven Central Repository:

```xml
    <dependency>
        <groupId>org.telegram</groupId>
        <artifactId>telegrambots</artifactId>
        <version>5.7.1</version>
    </dependency>
```

  2. Using Gradle: 

```gradle
    implementation 'org.telegram:telegrambots:5.7.1'
```

  3. Using Jitpack from [here](https://jitpack.io/#rubenlagus/TelegramBots/5.7.1)
  4. Download the jar(including all dependencies) from [here](https://mvnrepository.com/artifact/org.telegram/telegrambots/5.7.1)

In order to use Long Polling mode, just create your own bot extending `org.telegram.telegrambots.bots.TelegramLongPollingBot`.

If you like to use Webhook, extend `org.telegram.telegrambots.bots.TelegramWebhookBot`


Once done, you just need to create a `org.telegram.telegrambots.meta.TelegramBotsApi`and register your bots:

```java

    // Example taken from https://github.com/rubenlagus/TelegramBotsExample
    public class Main {
        public static void main(String[] args) {
            try {
                TelegramBotsApi telegramBotsApi = new TelegramBotsApi(DefaultBotSession.class);
                telegramBotsApi.registerBot(new ChannelHandlers());
                telegramBotsApi.registerBot(new DirectionsHandlers());
                telegramBotsApi.registerBot(new RaeHandlers());
                telegramBotsApi.registerBot(new WeatherHandlers());
                telegramBotsApi.registerBot(new TransifexHandlers());
                telegramBotsApi.registerBot(new FilesHandlers());
            } catch (TelegramApiException e) {
                e.printStackTrace();
            }
        }
    }

```




## Example bots
Open them and send them */help* command to get some information about their capabilities:

https://telegram.me/weatherbot (**Use custom keyboards**)

https://telegram.me/directionsbot (**Basic messages**)

https://telegram.me/filesbot (**Send files by file_id**)

https://telegram.me/TGlanguagesbot (**Send files uploding them**)

https://telegram.me/RaeBot (**Inline support**)

https://telegram.me/SnowcrashBot (**Webhook support**)



## Telegram Bot API
This library use [Telegram bot API](https://core.telegram.org/bots), you can find more information following the link.

