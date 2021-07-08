## General
vPerms is a real time permission system utilizting [vDiscord](https://github.com/VikingTheDev/vDiscord). The script was originally created by SpaceTheDev ([forums](https://forum.cfx.re/u/space_man), [github](https://github.com/SpaceTheDev)), so if you enjoy the script please show him some love. The only changes I have made to the script is adding some additional customizability in terms of the role hierarchy (adding subcategories), and making some minor changes to make it work with `vDiscord`. Check out the original release [here](https://forum.cfx.re/t/release-sperms-real-time-discord-perms/1686063).

The script is event based, meaning that it allows for real-time roles (no need for relogging or restarting the server for perms to update!). The perms are based on discord roles.

### Demo video:

<!-- blank line -->
<figure class="video_container">
  <video width="817" height="460" controls="true" allowfullscreen="true" poster="/assets/vPerms-poster.png">
    <source src="/assets/vPerms-demo.mp4" type="video/mp4">
  </video>
</figure>
<!-- blank line -->

## Installation

1. Install and configure [`vDiscord`](https://github.com/VikingTheDev/vDiscord), if you run into problems check out the [docs](docs.vikingthe.dev/fivem-docs/latest/projects/Discord/vDiscord/).

2. Download or clone the resource from this [repository](https://github.com/VikingTheDev/vPerms). 

2. Move `vPerms` into your resource folder and add ``ensure vPerms`` to your server.cfg.

!!! warning
    You have to configure the script before running it.

## Configuration

- Navigate to src/config.perms.json and open it.

- Change the categories/subcategories/roles to suit your needs. There's no limits to how many you can add. Watch the video below for a breakdown of how the permissions should be set up.

### Config breakdown:

<!-- blank line -->
<figure class="video_container">
  <video width="817" height="460" controls="true" allowfullscreen="true" poster="/assets/perms-breakdown-poster.png">
    <source src="/assets/perms-breakdown.mp4" type="video/mp4">
  </video>
</figure>
<!-- blank line -->

## Exports

### getPlayerPerms

Allows you to get the perms of a player (Server side).

#### Function
```js
const perms = getPlayerPerms(source);
```

| Parameter  | Type               | Description                                     | 
| :--------: | :----------------: | :---------------------------------------------: |
| ``source`` | Player source      | Source of the player you want to get perms for. |


!!! Info ""
    #### Example Code

    Config file used for the example:

    ```json
    {
      "permSetup": {
        "staff": {
          "adminstration": {
            "owner": "ID goes here",
            "admin": "ID goes here"
          },
          "moderation": {
            "mod": "ID goes here",
            "trial_mod": "ID goes here"
          },
          "developer": "ID goes here"
        }
      }
    }
    ```

    === "JS"

        ```js
        const perms = getPlayerPerms(source);
        console.log(perms)
        ```

        #### Output
        

        ```js
        {
          category: {
            staff: true / false
          },
          subcategory: {
            adminstration: true / false,
            moderation: true / false
          },
          staff: {
            adminstration: {
              owner: true / false,
              admin: true / false
            },
            moderation: {
              mod: true / false,
              trial_mod: true / false
            },
            developer: true / false
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
          category: {
            staff: true / false
          },
          subcategory: {
            adminstration: true / false,
            moderation: true / false
          },
          staff: {
            adminstration: {
              owner: true / false,
              admin: true / false
            },
            moderation: {
              mod: true / false,
              trial_mod: true / false
            },
            developer: true / false
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
          category: {
            staff: true / false
          },
          subcategory: {
            adminstration: true / false,
            moderation: true / false
          },
          staff: {
            adminstration: {
              owner: true / false,
              admin: true / false
            },
            moderation: {
              mod: true / false,
              trial_mod: true / false
            },
            developer: true / false
          }
        }
        ```

## Events

### setPerms

Event triggered when perms are set for a user (Client side).

#### Function
```js
onNet('vPerms:setPerms', ( perms ) => { } );
```

| Parameter  | Type   | Description                                     | 
| :--------: | :----: | :---------------------------------------------: |
| ``perms``  | Object | Object containing all permissisons for the user |


!!! Info ""
    #### Example Code

    Config file used for the example:

    ```json
    {
      "permSetup": {
        "staff": {
          "adminstration": {
            "owner": "ID goes here",
            "admin": "ID goes here"
          },
          "moderation": {
            "mod": "ID goes here",
            "trial_mod": "ID goes here"
          },
          "developer": "ID goes here"
        }
      }
    }
    ```

    === "JS"

        ```js
        onNet('vPerms:setPerms', ( perms ) => {
          console.log(perms);
        });
        ```

        #### Output
        

        ```js
        {
          category: {
            staff: true / false
          },
          subcategory: {
            adminstration: true / false,
            moderation: true / false
          },
          staff: {
            adminstration: {
              owner: true / false,
              admin: true / false
            },
            moderation: {
              mod: true / false,
              trial_mod: true / false
            },
            developer: true / false
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
          category: {
            staff: true / false
          },
          subcategory: {
            adminstration: true / false,
            moderation: true / false
          },
          staff: {
            adminstration: {
              owner: true / false,
              admin: true / false
            },
            moderation: {
              mod: true / false,
              trial_mod: true / false
            },
            developer: true / false
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
          category: {
            staff: true / false
          },
          subcategory: {
            adminstration: true / false,
            moderation: true / false
          },
          staff: {
            adminstration: {
              owner: true / false,
              admin: true / false
            },
            moderation: {
              mod: true / false,
              trial_mod: true / false
            },
            developer: true / false
          }
        }
        ```