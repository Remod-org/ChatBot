# ChatBot

Chat bot for Rust using ChatGPT to get short answers to basic questions... eventually.

This is a proof of concept, and it's free.  Much of the information used to construct it was from:

  - https://www.c-sharpcorner.com/article/chatgpt-completions-with-c-sharp/

You must disable the oxide sandbox - see  https://umod.org/guides/oxide/disabling-plugin-sandboxing

You may also need to adjust/remove UFilter, BetterChat, et al.  ymmv

## Configuration
```cs
{
  "Options": {
    "apiKey": "",
    "keyWord": "bot?",
    "requirePermission": false,
    "ChatIcon": "76561199467638159"
  },
  "debug": true,
  "Version": {
    "Major": 1,
    "Minor": 0,
    "Patch": 1
  }
}
```

You will need to create an API key at perhaps https://beta.openai.com/account/api-keys.

Save the key somewhere safe and add it to the config above at "apiKey": "HERE"

Answers may be slow unless and when a paid account is available and implemented.

The keyWord can be changed, but will only be checked at the start of a chat message, e.g. "bot? hello?" not "was that a bot?"

## Permissions

  - chatbot.use -- if the configuration item requirePermission is set to true, players will need to have this permissions in order to query the bot.

## Usage

The player will need to have the 'chatbot.use' permission (if required).

Beyond that, usage is simply to type something like the following in chat.  Note: DO NOT USE /

  - bot? What is the game Rust?


Responses will eventually be delivered to ALL players.  There is nothing private about this, currently.

