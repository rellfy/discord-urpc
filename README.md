# discord-µrpc
A simpler RPC client for Discord

## Example: Rich Presence

```js
const DiscordRPC = require('discord-urpc');
const uRPC = new DiscordRPC({ clientID: 'xxxxxxxxxxxxxxxxxx', debug: true || false });

uRPC.on('ready', () => {
    const args = {
        pid: process.pid,
        activity: {
            state: 'Game State',
            details: 'Game Details',
            timestamps: {
                start: new Date().getTime() / 1000
            },
            assets: {
                large_image: 'discord-asset-key-1',
                large_text: 'image 1',
                small_image: 'discord-asset-key-2',
                small_text: 'image 2',
            },
            // party,
            // secrets,
            instance: false
        }
    };

    uRPC.send('SET_ACTIVITY', args);
});
```