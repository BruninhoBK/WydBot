WydBot
=====

Introduction
-----

WydBot is a Supreme Destiny bot API written in Python.
It is designed to be easy to use and uses the event-listener pattern.

Current features
------

 - Joining servers
 - Authenticate on server
 - Unlock pincode / Select Characters
 - Enter world
 - Parsing server data to keep classes up-to-date
 - Moving the bot by Pathfinding
 - Triggering various events (Chatting / NewEntry / StatusEntry).


Examples
-------

The following is a very basic bot, which will connect and handle chat.

-----
```python
from wydbot import WydBot
from wydbot.events import Events

# Create a WydBot object
bot = WydBot('127.0.0.1')
event = bot.get_event_manager()


# Connect a function to an event using a decorator
@event.on_event(Events.Chat)
def chat(event_id, msg):
    # Do something with the message
    # In this case, stop the bot if the word "Stop" occurs
    print(msg)
    if "stop" in msg:
        bot.stop()


# Start the bot
bot.start()

# And wait
while bot.client.running:
    pass

```

More examples can be found under the 'examples' directory. Also check the wiki for more information about the inner workings of the bot and how to interface with it.

Contributing
--------

If you want to contribute, that's great! I would really appreciate the help. Just send a pull request and i'll quickly check and accept it. These are some areas that need work:

- Item dropping
- Synchronizing packets like health and others.
- Read Env/fields????.dat, to generate the map grid.
