# Programmable Discord Bot
A intuitive and hassle-free way to program a Discord Bot.
1. Zero setup
2. Script Discord APIs in chat

## Invite links

* Click on this [link](https://bit.ly/stensal) to add me as JS script eval bot.
  You can run pure JS scripts with limited capability to access Discord APIs
  
* Click on this [link](https://bit.ly/38LFRrS) to add me to manage your messages.
  Give the bot the permission to manage your server's messages so you can script messages.

* Click on this [link](https://bit.ly/3fN0NmD) to add me as an admin.
  Give the bot the admin permission, so you can script all things you can do manually.
  As this is risky, please invite the bot to your test servers only.
    

## Commands

### Display help
```
!h
```

### Delete results
```
!d
```

### Run a script in JS (ES5) Syntax
```
!r  "Hello World"
```

```
!r 1+1
```

```
!r ```js
console.log("Hello World!");```
```

## Scripting Discord APIs
NOTE: To get a channel id (channel_id) or message id (message_id), right-click on either the channel or the message and select `Copy ID` in the menu.

### Display the information of the discord user who ran this command
```
!r  runner
```

### Display the discord user structure of whoever runs this command
```
!r  cee.get_user(runner.id)
```


### Get the current channel infomation in JSON
```
!r cee.get_channel(runner.channel_id)
```

### Modify the current channel
```
!r cee.modify_channel(runner.channel_id, { name:"a-new-channel-name" })
```

### Delete the current channel
```
!r cee.delete_channel(runner.channel_id);
```

### Get Channel Messages
```
!r cee.get_channel_messages(runner.channel_id);
```

```
// One message
!r var msgs = cee.get_channel_messages(runner.channel_id);
msgs[0];
```

```
// Print out the author of each message
!r ```js
  var msgs = cee.get_channel_messages(runner.channel_id);
  for (var i in msgs)
    console.log(msgs[i].author.username)```
 
```

### Get channel message
```
!r cee.get_channel_message(runner.channel_id, runner.message_id);
```

### Create a message
```
!r cee.create_message(runner.channel_id, { content: "Hello World!" });
```

### Create a reaction
```
!r ```js
var heart = transformer.url_encode("❤️");
cee.create_reaction(runner.channel_id, runner.message_id, heart);```
```


### Get all users who react to an emoji
```
!r ```js
var play = transformer.url_encode("▶️");
var users = cee.get_reactions(runner.channel_id, runner.message_id, play);
for (var i in users)
  console.log(users[i]);```
```

### Delete all reactions of a message
```
!r cee.delete_all_reactions(runner.channel_id, runner.message_id)
```

### Delete all reactions for an emoji
```
!r ```js
var play = transformer.url_encode("▶️");
cee.delete_all_reactions_for_emoji (runner.channel_id, runner.message_id, play);```
```

### Edit a message
```
!r cee.edit_message(runner.channel_id, <message_id>, { content: "!r console.log(1)" });
```

### Delete a message
```
!r cee.delete_message(runner.channel_id, runner.message_id);
```

### Bulk delete messages
```
!r cee.bulk_delete_messages(runner.channel_id, [<message-ids>]);
```

### Edit Channel Permissions
```
!r cee.edit_channel_permissions(runner.channel_id, overwrite_id, params);
```


### Get Channel Invites
```
!r cee.get_channel_invites(runner.channel_id);
```

## Trigger Typing Indicator
```
!r cee.trigger_typing_indicator(runner.channel_id);
```

## Get Guild Channels
```
!r ```js
var l = cee.get_guild_channels(runner.guild_id);
for(var i in l)
  console.log(l[i]);```


!r ```js
var l = cee.get_guild_channels(runner.guild_id);
for(var i in l)
  console.log(l[i].name + ":" + l[i].type);```

```

## Create guild channel
```
!r cee.create_guild_channel(runner.guild_id, { name:"a-new-channel" });
```

## List guild members
```
!r  cee.list_guild_members(runner.guild_id);
```
