# Open Source - Chat for alt:V

Created by Dzeknjak (Jovan Ivanovic)

❤️ Please support my open source work by donating. I'm here to provide general context for complicated procedures for you new developers. ❤️

https://www.buymeacoffee.com/dzeknjak

⭐ This repository if you found it useful!

---

![](https://i.imgur.com/5NUVhNU.png)

# Description

Simple chat implementation for alt:V to get your server started with some player-to-player interaction.

# Usage

There's couple of events to get you started with this resource:

```javascript
// Notice: these events are mainly serverside unless otherwise stated
```

---

## Initializing the chat

```javascript
// Notice: you should probably call this event on player connect or when the player logs in, it's up to you, but it needs to be called for it to work.
```

```javascript
alt.emit('chat:Init', key);
```

| Argument | Description                                                              |
| -------- | ------------------------------------------------------------------------ |
| `key`    | `[optional]` Keyboard key to trigger the chat input. Default key is `T`. |

To find a keycode, go to this website: [JavaScript Event KeyCodes](http://keycode.info/)

---

## Sending a message to player(s)

```javascript
alt.emit('chat:Message', recipient, message);
```

| Argument    | Description                                                                                             |
| ----------- | ------------------------------------------------------------------------------------------------------- |
| `recipient` | Either an instance of `alt.Player` or an array of players to whom you want to send the message to.      |
| `message`   | Message you want to send to the players. You can use `{FFFFFF}` formating to set colors in the message. |

## Broadcasting a message to all players

```javascript
alt.emit('chat:Broadcast', message);
```

| Argument  | Description                                                                                                  |
| --------- | ------------------------------------------------------------------------------------------------------------ |
| `message` | Message you want to broadcast to the players. You can use `{FFFFFF}` formating to set colors in the message. |

## Toggling the visibility of the chat

```javascript
// Notice: this event is clientside only.
```

---

```javascript
alt.emit('chat:Toggle', state);
```

| Argument | Description                                                                                                             |
| -------- | ----------------------------------------------------------------------------------------------------------------------- |
| `state`  | `[optional]` Sets the visibility state of the chat. If not set, it will show/hide according to the current state of it. |

## Working with player's messages

Scrolling the chat is done simply by pressing `Page Up` or `Page Down` keys on your keyboard.

## Working with player's messages

> This resource doesn't automatically append messages to the chat window. It is up to you how you want to manipulate the messages, to whom to send them or to parse them as commands.

```javascript
alt.on('chat:NewMessage', (player, message) => {
    // Do your thing here
});
```

| Argument  | Description                                                |
| --------- | ---------------------------------------------------------- |
| `player`  | `alt.Player` instance of the player that sent the message. |
| `message` | The message text that the player sent.                     |

# Other alt:V Open Source Resources

-   [Authentication by Stuyk](https://github.com/Stuyk/altv-os-auth)
-   [Global Blip Manager by Dzeknjak](https://github.com/jovanivanovic/altv-os-global-blip-manager)
-   [Global Marker Manager by Dzeknjak](https://github.com/jovanivanovic/altv-os-global-marker-manager)
