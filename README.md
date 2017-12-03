# Telegram-self-bot-for-fancy-stuff

This is basically your regular telegram-cli (tdcli) with a Lua script on top that takes care of things for you quickly and translaprently. You cannot interact with the bot until you write code for it.

In its current revision it does these things:

<h3><b>1. Pseudo Undelete capability.</b></h3>

In reality it forwards all incoming text messages to your contact's chat in Telegram, effectively creating a sequential log of all incoming messages. The messages are forwarded, preserving the author's name. 

TODO: Add some sort of hash-based way to sort the messages, add a way to configure exclusions. Add checking freshly edited messages for tags. Process multiple tags in one messages (currently doesn't work).

<h3><b>2. Strikethrough tag.</b></3>

The script also parses all messages that are outgoing and have just been delivered. If the message contains text inside ~ ~ tags, the script replaces it with its ̶s̶t̶r̶i̶k̶e̶s̶ ̶t̶h̶r̶o̶u̶g̶h̶ equivalent by editing the message for you. Currently there is no convenient way to avoid the marking the message edited because its id may yet change until it's been delivered.

ADDED: Support for Russian strikethrough

TODO: Add more fancy stuff! Add more aliases. Figure out lua_register_function.

<h3><b>Requirements</h3></b>

You will need lua-utf8 built for Lua5.2 or higher. If you're getting Lua errors check that your compiler's includes do not include lua/5.1. I tried to keep the rest as vanilla as possible.

The script uses tdcli-1222.

<h3><b>Usage</h3></b>

On Telegram, message @JsonDumpBot and find out your chat.id; add it to the script.

<pre>./tdcli-1222 -s script.lua</pre>

(You will need to fully authorize yourself the first time.)

Binary tdcli-1222 included for build compatibility reasons only, please get a binary you trust.
