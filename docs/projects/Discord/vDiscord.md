## General

vDiscord is an API that allows you to interact with a [Discord Bot](https://discord.com/developers/docs/intro#bots-and-apps). The resource comes in two "pieces", the API itself that runs outside of the server, and vConnect. The API and vConnect uses a websocket to communicate, meaning all interactions are instantaneous.

### Why the websocket?

Discord.js won't run on server due some compatability issues. There used to be a forked version of discord.js that ran on server, but it stopped working for me, so I had to write an API instead. Although it's annoying having to run it outside the server, it brings the benefit of being able to run the latest version of discord.js.

## Installation

### Prerequisites#
Node.js (download [here](https://nodejs.org/en/)) and a discord bot in your community's discord server (You can create a bot [here](https://discord.com/developers/applications)).

### Steps

1. Download or clone the resource from this [repository](https://github.com/VikingTheDev/vDiscord). When you open the downloaded folder you will find two folders; `vConnect` and `vAPI`. 

2. Move `vConnect` into your resource folder and add ``ensure vConnect`` to your server.cfg. Open a command-line interface (CMD, Bash, Powershell etc.), and navigate to the `vConnect` folder. Type ``npm install``, and wait for npm to install all dependencies.

3. Move `vAPI` to a location of your choice *outside* of the server files i.e. the desktop. Open your CLI and navigate to the `vAPI` folder. Type the following ``npm install`` and wait for npm to install all dependencies. To start the API, navigate to the folder in your CLI and type ``node src/index.js``. I'd recommend setting up a .bat file for this so that you don't have to check the docs everytime you want to start the API. 

It does not matter if you start the API before or after the server, or if you close and reopen it while the server is running. When `vConnect` connects to `vAPI` a message will be logged in both consoles.

*[CLI]: Command-line Interface
*[npm]: Node Package Manager

!!! warning
    You have to configure both scripts before running them.

## Configuration

### vAPI

- Open ``config.api.json``.
- Change ``botToken`` to the token of the discord bot you're using (https://discord.com/developers/applications).
- Change ``guildId`` to the ID of you community's discord server (Enable developer mode on discord, right click your server and press "Copy ID").
- Change ``websocketToken`` to a token of your choice, this is to ensure no unauthorized connections take place so it should preferably be something hard to guess.

### vConnect

- Open ``config.json``.
- Change ``queryToken`` to the same token as ``websocketToken``. Again, make it secure as this is to prevent unauthorized connections.

## Exports

### user

Methods for interacting with a user, currently used for adding/removing roles, sending DMs and moving a user to a VC.

#### Function
```js
user(type, data, cb => {});
```

| Parameter | Type               | Description                                                                 | 
| :-------: | :----------------: | :-------------------------------------------------------------------------: |
| ``type``  | String             | Used to define which type of interaction you want to use                    |
| ``data``  | Object *or* String | Object containing data neccessary for the function, see below for more info |
|  ``cb``   | Callback           | Callback returning an object with a status message (success or error)       |

#### Types

##### roleAdd

Used for adding a role to a user.

``data`` object structure:

| Parameter | Type   | Description                              | 
| :-------: | :----: | :--------------------------------------: |
| ``user``  | String | ID of the user you're adding the role to |
| ``role``  | String | ID of the role you wish to add           |

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        exports.discord.user("roleAdd", {
            user: "230347924951793664",
            role: "774617965337247765"
        }, cb => {
            console.log(cb)
        });
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

##### roleRemove

Used for removing a role to from user.

``data`` object structure:

| Parameter | Type   | Description                                  | 
| :-------: | :----: | :------------------------------------------: |
| ``user``  | String | ID of the user you're removing the role from |
| ``role``  | String | ID of the role you wish to remove            |

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        exports.discord.user("roleRemove", {
            user: "230347924951793664",
            role: "774617965337247765"
        }, cb => {
            console.log(cb)
        });
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

##### moveVC

Used for moving a user to a different VC.

``data`` object structure:

| Parameter    | Type   | Description                                 | 
| :-------:    | :----: | :-----------------------------------------: |
| ``user``     | String | ID of the user you're moving                |
| ``channel``  | String | ID of the channel you're moving the user to |

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        exports.discord.user("moveVC", {
            user: "230347924951793664",
            channel: "811258115537371186"
        }, cb => {
            console.log(cb)
        });
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

##### sendDM

Used for sending a DM to a user.

``data`` object structure:

| Parameter    | Type               | Description                                         | 
| :-------:    | :----------------: | :-------------------------------------------------: |
| ``user``     | String             | ID of the user you're messaging                     |
| ``message``  | String *or* Object | Message content either as string or an embed object |

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        exports.discord.user("semdDM", {
            user: "230347924951793664",
            message: "Hi :)"
        }, cb => {
            console.log(cb)
        });
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output
        

        ```js
        {
            "err": true / false,
            "message": status_message
        }

        ```



### sendLogMsg

Export used to send regualar and embed messages to a channel, intended to be used for logging.

#### Function
```js
    sendLogMsg(type, channel, data, cb => {});
```

| Parameter    | Type               | Description                                                                                        | 
| :----------: | :----------------: | :------------------------------------------------------------------------------------------------: |
| ``type``     | String             | Used to define which type of message you want to send                                              |
| ``channel``  | String             | Used to define which channel the message should be sent to                                         |
| ``data``     | Object *or* String | Object or string containing message data, content depends on type, see below for more info on this |
| ``cb``       | Callback           | Callback returning a bool and an object containing message info/any error messages                 |

#### Types

##### regular

Used for sending a regular message to a channel, takes a string as ``data``.

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        const channel = "*textchannel id*";
        const message = "Hello World!";
        exports.discord.sendLogMsg("regular", channel, message, cb => {
            console.log(cb)
        });
        ```

        #### Output

        If the channel is valid and the message is successfully delivered:

        ```js
        {
            "sent": true,
            "id": "*message id*",
            "channelId": "*id of textchannel*"
        }
        ```

        If the channel is invalid or some other error occurs:

        ```js
        {
            "sent": false,
            "error": err.message
        }
        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output

        If the channel is valid and the message is successfully delivered:

        ```lua
        {
            "sent": true,
            "id": "*message id*",
            "channelId": "*id of textchannel*"
        }
        ```

        If the channel is invalid or some other error occurs:

        ```lua
        {
            "sent": false,
            "error": err.message
        }
        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output

        If the channel is valid and the message is successfully delivered:

        ```cs
        {
            "sent": true,
            "id": "*message id*",
            "channelId": "*id of textchannel*"
        }
        ```

        If the channel is invalid or some other error occurs:

        ```cs
        {
            "sent": false,
            "error": err.message
        }
        ```

##### embed

Used for sending a embed message to a channel, takes an object as ``data``.

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        const channel = "*textchannel id*";
        const embedobj = { 
            "content": "<@&767803636926906419>",
            "embed": {
                author: {
                name: "Name of author",
                iconURL: "https://cdn.discordapp.com/attachments/562656258415525898/571040114277613598/officialssrplogo.png"
                },
                color: "12745742",
                title: "This is a title",
                description: "This is a description",
                fields: [
                {
                    name: "field1",
                    value: "field 1 text"
                },
                {
                    name: "field2",
                    value: "field 2 text"
                }
                ],
                footer: {
                    text: "Test © Petrikov",
                    iconURL: "https://cdn.discordapp.com/attachments/562656258415525898/571040114277613598/officialssrplogo.png"
                },
                timestamp: Date.now()
            }
        }
        exports.discord.sendLogMsg("embed", channel, embedobj, cb => {
            console.log(cb)
        })
        ```

        #### Output

        If the channel is valid and the message is successfully delivered:

        ```js
        {
            "sent": true,
            "id": "*message id*",
            "channelId": "*id of textchannel*"
        }
        ```

        If the channel is invalid or some other error occurs:

        ```js
        {
            "sent": false,
            "error": err.message
        }
        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output

        If the channel is valid and the message is successfully delivered:

        ```lua
        {
            "sent": true,
            "id": "*message id*",
            "channelId": "*id of textchannel*"
        }
        ```

        If the channel is invalid or some other error occurs:

        ```lua
        {
            "sent": false,
            "error": err.message
        }
        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output

        If the channel is valid and the message is successfully delivered:

        ```cs
        {
            "sent": true,
            "id": "*message id*",
            "channelId": "*id of textchannel*"
        }
        ```

        If the channel is invalid or some other error occurs:

        ```cs
        {
            "sent": false,
            "error": err.message
        }
        ```

### getUserData

Returns an object containing user data.

#### Function

```js
getUserData(user, cb => {});
```

| Parameter    | Type     | Description                                       | 
| :----------: | :------: | :-----------------------------------------------: |
| ``user``     | String   | The ID of the user you're fetching data for.      |
| ``cb``       | Callback | Callback returning the data object *or* undefined |

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        const userId = "*userID*";
        exports.discord.getUserData(user, (completed, data) => {
            console.log(completed, data)
        })
        ```

        #### Output

        If the user id is valid and the bot can successfully gather the data:

        ```js
        {
            "id": "*users ID*",
            "guildId": "*guild ID*",
            "tag": "username#0000",
            "displayName": "*users displayname in guild*",
            "roles": [
                "role 1 id",
                "role 2 id",
                "role 3 id"
            ]
        }
        ```

        If the user id is invalid or some other error occurs: (Error info will be logged in console)


        ```js
        undefined
        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output

         If the user id is valid and the bot can successfully gather the data:

        ```lua
        true {
            "id": "*users ID*",
            "guildId": "*guild ID*",
            "tag": "username#0000",
            "displayName": "*users displayname in guild*",
            "roles": [
                "role 1 id",
                "role 2 id",
                "role 3 id"
            ]
        }
        ```

        If the user id is invalid or some other error occurs:


        ```lua
        false *error message ex. "Cannot read property 'user' of undefined"*
        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output

         If the user id is valid and the bot can successfully gather the data:

        ```cs
        true {
            "id": "*users ID*",
            "guildId": "*guild ID*",
            "tag": "username#0000",
            "displayName": "*users displayname in guild*",
            "roles": [
                "role 1 id",
                "role 2 id",
                "role 3 id"
            ]
        }
        ```

        If the user id is invalid or some other error occurs:


        ```cs
        false *error message ex. "Cannot read property 'user' of undefined"*
        ```

### checkDiscordBan

Checks if a user is banned in the guild specified in the config.

```js
checkDiscordBan(user, cb => {});
```

| Parameter    | Type     | Description                                                                | 
| :----------: | :------: | :------------------------------------------------------------------------: |
| ``user``     | String   | The ID of the user you're checking.                                        |
| ``cb``       | Callback | Callback returning a bool and the reason for the ban *or* an error message |

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        const user = "*userID*"
        exports.jsbase.checkDiscordBan(user, (bool, reason) => {
            console.log(bool, reason);
        });
        ```

        #### Output

        If the user is banned:

        ```js
        { 
            state: true,
            reason: "*Reason for ban*"
        }
        ```

        If the user is not banned:

        ```js
        { 
            state: false,
            reason: undefined
        }
        ```

        If an error occured:

        ```js
        { 
            state: false,
            reason: "*error message*"
        }
        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output

        If the user is banned:

        ```lua
        { 
            state: true,
            reason: "*Reason for ban*"
        }
        ```

        If the user is not banned:

        ```lua
        { 
            state: false,
            reason: undefined
        }
        ```

        If an error occured:

        ```lua
        { 
            state: false,
            reason: "*error message*"
        }
        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output

        If the user is banned:

        ```cs
        { 
            state: true,
            reason: "*Reason for ban*"
        }
        ```

        If the user is not banned:

        ```cs
        { 
            state: false,
            reason: undefined
        }
        ```

        If an error occured:

        ```cs
        { 
            state: false,
            reason: "*error message*"
        }
        ```

## Events

### guildMemberUpdate

Is triggered when a user is updated in the guild, i.e. name, roles etc.

#### Server side event

```js
on('vConnect:guildMemberUpdate', ( m ) => {} );
```

| Parameter | Type     | Description                                                        | 
| :-------: | :------: | :----------------------------------------------------------------: |
| ``m``     | Callback | Callback returning an object with info on updated the guild member |

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        on('vConnect:guildMemberUpdate', (m) => {
            console.log(m);
        });
        ```

        #### Output

        ```js
        {
            "id": "*users ID*",
            "guildId": "*guild ID*",
            "tag": "username#0000",
            "displayName": "*users displayname in guild*",
            "roles": [
                "role 1 id",
                "role 2 id",
                "role 3 id"
            ]
        }
        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output

         If the user id is valid and the bot can successfully gather the data:

        ```lua
        true {
            "id": "*users ID*",
            "guildId": "*guild ID*",
            "tag": "username#0000",
            "displayName": "*users displayname in guild*",
            "roles": [
                "role 1 id",
                "role 2 id",
                "role 3 id"
            ]
        }
        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output

         If the user id is valid and the bot can successfully gather the data:

        ```cs
        true {
            "id": "*users ID*",
            "guildId": "*guild ID*",
            "tag": "username#0000",
            "displayName": "*users displayname in guild*",
            "roles": [
                "role 1 id",
                "role 2 id",
                "role 3 id"
            ]
        }
        ```

#### Client side event
Functions exactly same way as the server side event, but will be triggered in client scripts (Currently triggers on ALL clients, which might not be optimal. Expect possible change here).

```js
onNet('vConnect:guildMemberUpdate', ( m ) => {} );
```

| Parameter | Type     | Description                                                        | 
| :-------: | :------: | :----------------------------------------------------------------: |
| ``m``     | Object   | Callback returning an object with info on updated the guild member |

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        onNet('vConnect:guildMemberUpdate', (m) => {
            console.log(m);
        });
        ```

        #### Output

        ```js
        {
            "id": "*users ID*",
            "guildId": "*guild ID*",
            "tag": "username#0000",
            "displayName": "*users displayname in guild*",
            "roles": [
                "role 1 id",
                "role 2 id",
                "role 3 id"
            ]
        }
        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output

         If the user id is valid and the bot can successfully gather the data:

        ```lua
        true {
            "id": "*users ID*",
            "guildId": "*guild ID*",
            "tag": "username#0000",
            "displayName": "*users displayname in guild*",
            "roles": [
                "role 1 id",
                "role 2 id",
                "role 3 id"
            ]
        }
        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output

         If the user id is valid and the bot can successfully gather the data:

        ```cs
        true {
            "id": "*users ID*",
            "guildId": "*guild ID*",
            "tag": "username#0000",
            "displayName": "*users displayname in guild*",
            "roles": [
                "role 1 id",
                "role 2 id",
                "role 3 id"
            ]
        }
        ```

### guildBanAdd

Is triggered when a user is banned in the guild.

#### Server side event

```js
on('vConnect:guildBanAdd', ({ guildId, userInfo, reason }) => { } );
```

| Parameter    | Type     | Description                                             | 
| :----------: | :------: | :-----------------------------------------------------: |
| ``guildId``  | String   | The ID of the guild the user was banned in              |
| ``userInfo`` | Object   | Object containing info about the user (id and username) |
| ``reason``   | String   | The reason for the ban                                  |

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        on('vConnect:guildBanAdd', ({ guildId, userInfo, reason }) => { 
            console.log({ guildId, userInfo, reason });
        });
        ```

        #### Output

        ```js
        {
            guildId: "*id of the guild*",
            userinfo: {
                id: "*id of the banned user*",
                username: "*the users name*"
            },
            reason: "*reason for the ban*"
        }
        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output

        ```lua
        {
            guildId: "*id of the guild*",
            userinfo: {
                id: "*id of the banned user*",
                username: "*the users name*"
            },
            reason: "*reason for the ban*"
        }
        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output

        ```cs
        {
            guildId: "*id of the guild*",
            userinfo: {
                id: "*id of the banned user*",
                username: "*the users name*"
            },
            reason: "*reason for the ban*"
        }
        ```

### guildBanRemove

Is triggered when a user is unbanned in the guild.

#### Server side event

```js
on('vConnect:guildBanRemove', ({ guildId, userInfo}) => { } );
```

| Parameter    | Type     | Description                                             | 
| :----------: | :------: | :-----------------------------------------------------: |
| ``guildId``  | String   | The ID of the guild the user was unbanned in            |
| ``userInfo`` | Object   | Object containing info about the user (id and username) |

!!! Info ""
    #### Example Code
    === "JS"

        ```js
        on('vConnect:guildBanRemove', ({ guildId, userInfo}) => { 
            console.log({ guildId, userInfo});
        });
        ```

        #### Output

        ```js
        {
            guildId: "*id of the guild*",
            userinfo: {
                id: "*id of the unbanned user*",
                username: "*the users name*"
            }
        }
        ```

    === "LUA"

        ```lua
        #To-come
        ```

        #### Output

        ```lua
        {
            guildId: "*id of the guild*",
            userinfo: {
                id: "*id of the unbanned user*",
                username: "*the users name*"
            }
        }
        ```

    === "C#"

        ```cs
        #To-come
        ```

        #### Output

        ```cs
        {
            guildId: "*id of the guild*",
            userinfo: {
                id: "*id of the unbanned user*",
                username: "*the users name*"
            }
        }
        ```