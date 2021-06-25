# Build a Telegram Bot

## Context
Your team need to be notified when something happen in the system.
For example, a SysOps Engineer need to run a script that will take
a long time to finished, and he need to know the result of the script.
He run something like this:

    #!/bin/bash

    notify_telegram "Executing script to clean up garbage in the servers"
    ./clean-up-garbage.sh
    return_code=$?
    notify_telegram "Script clean up garbage finished with code $return_code"

## Task
Write a Python program to send a message to Telegram with these requirements:
- use Python version >= 3.6
- executable by Bash, like the example above
- configurable at run time, the user can send message to another Telegram bot.
You are free to choose the file format of your config file,
or how the program read the config file. For example:

```
notify_telegram "Script clean-up.sh finished"
notify_telegram -c ./data-team-telegram.conf \
    "Hi data team, your server is cleaned up and ready to use."
```

- callable as a Python function, example:

```
#!/usr/bin/env python3
import telegram_bot as tb

bot = tb.TelegramBot()
bot.notify("Script clean-up.sh finished")

bot2 = tb.TelegramBot(config_path="./data-team-telegram.conf")
bot.notify("Hi data team, your server is cleaned up and ready to use.")
```
