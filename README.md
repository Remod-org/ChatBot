# ChatBot

Chat bot for Rust using ChatGPT to get short answers to basic questions.

This is a proof of concept, and it's free.  However, the request made to the API will incur a cost assuming it is not still in beta and depending on what arrangement you make with openai.com.

Much of the information used to construct it was borrowed from:

  - https://www.c-sharpcorner.com/article/chatgpt-completions-with-c-sharp/

You must disable the oxide sandbox - see  https://umod.org/guides/oxide/disabling-plugin-sandboxing

You may also need to adjust/remove UFilter, BetterChat, et al.  ymmv.

## Configuration
```cs
{
  "Options": {
    "apiKey": "",
    "model": "text-ada-001",
    "keyWord": "bot?",
    "requirePermission": false,
    "ChatIcon": "76561199467638159"
  },
  "debug": true,
  "Version": {
    "Major": 1,
    "Minor": 0,
    "Patch": 5
  }
}
```

You will need to create an API key at perhaps https://beta.openai.com/account/api-keys.

Save the key somewhere safe and add it to the config above at "apiKey": "HERE"

The cost of the requests depends on the model used.  We default to the cheapest:

  - text-davinci-003 (expensive)
  - text-curie-001 (less expensive)
  - text-babbage-001 (less so)
  - text-ada-001 (cheapest, default)

See https://beta.openai.com/docs/models/gpt-3 for more information on these models.
See https://openai.com/api/pricing/ for pricing per request...

The keyWord can be changed, but will only be checked at the start of a chat message, e.g. "bot? hello?" not "was that a bot?"

## Permissions

  - chatbot.use -- if the configuration item requirePermission is set to true, players will need to have this permission in order to query the bot.

## Usage

The player will need to have the 'chatbot.use' permission (if required).

Beyond that, usage is simply to type something like the following in chat.  Note: DO NOT USE SLASH '/'

  - bot? What is the game Rust?


Responses will be delivered to ALL players if in Global chat, and Team members if in Team chat.


