# Description

EasyVotePro brings you 2 new voting websites, Discord Embeds, SimpleStatus, and UINotify/Notify! With frequent updates, a dedicated support section, and more, growing your server has never been easier!

Players receive a reward every time they vote successfully. You can edit the available rewards in the configuration file.

Add custom reward based how many time player has voted. You can add many as you like custom rewards, there is no limits.

Supports Rust-Servers.net, RustServers.gg, BestServers.com, TrackyServer.com, GamesFinder.net, and Top-Games.net.

And much more!

**THIS PLUGIN IS IN BETA STAGES RIGHT NOW! BE SURE TO TEST THIS PLUGIN ON A TEST SERVER FIRST! Everything works just fine, however its still in active development and you may come across a bug or two especially when I release a newer version. Please open a ticket to report the bug so it can get fixed.**

## General Features

- Ability to control when a player gets notified that they have unclaimed votes/need to vote

- Rewards are now strictly command based. Just put in your command in the reward section and you're off!
- You can now change the description for each reward whenever a player runs the /rewardlist command
- Added useful command line command to check players vote count, reset their vote count and more
- Added an option to reset a players vote count whenever a map wipes
- Added useful debug options for easier debugging
- Ability to add as many reward tiers as you want! All you have to do is change the number under rewards to the amount of votes a player needs for those rewards to be given.
- You can now completely disable the /vote command. Why? Because it was requested. I don't see the point of this, but its there.
- No more EasyVotePro permissions system!
- You can now click on the vote link RIGHT FROM THE CHAT BOX! No need to give notes to players anymore! However, that option still exists if you want to use it.

## Support For EasyVotePro

All support for this plugin has been moved to my Discord server. This is due to the sensitive nature of API keys being in the config, and generally me asking to see your configuration file. If you post your configuration file in the support section of Codefling, it will be public for all to see. Plus you'll get faster support for the plugin if you use Discord. A link to my Discord server is above, just click on the big image at the top of this description.

I need you to do two things when you open a ticket in my Discord for this plugin. Enable debug mode (Only debug mode, not verbose debug) and run the plugin for a while with debug mode enabled. Try and replicate whatever bug you came across with that debug mode enabled. Then I need you to send me your log file. The full log file, not just the one in the /logs/EasyVotePro. I need the carbon or oxide log file. Also send me a copy of your configuration AND your voting links for each site you've signed up for so that I can test the votes on my end.

## Chat Commands

`/vote` -- Show vote link(s)

`/claim` -- Claim vote reward(s)

`/rewardlist` -- Display what reward(s) can get

## Console Commands

`evp.clearplayer <steamID>` - Clears a players vote count to 0

`evp.setvote <steamID> <voteCount>` - Set the players vote count to a specific number

`evp.resetall` - Resets all voting data for every player

## Plugin API Hooks

```
// Returns an int value of the number of votes a player has
(int) getPlayerVotes(string steamID)
```

## Configuration

The settings and options for this plugin can be configured in the EasyVoteLite.json file in the config directory. The use of a JSON editor or validation site such as jsonlint.com is recommended to avoid formatting issues and syntax errors.

```
{
  "Debug Settings": {
    "Debug Mode Enabled?": true,
    "Enable Verbose Debugging? (READ DOCUMENTATION FIRST!)": false,
    "Set Check API Response Code (0 = Not found, 1 = Has voted and not claimed, 2 = Has voted and claimed)": 1,
    "Set Claim API Response Code (0 = Not found, 1 = Has voted and not claimed. The vote will now be set as claimed., 2 = Has voted and claimed": 1,
    "SteamID used for debug console commands": "INSERT_ID",
    "Username used for debug console commands": "INSERT_USERNAME"
  },
  "Plugin Settings": {
    "Enable logging => logs/EasyVotePro (true / false)": true,
    "Wipe Rewards Count on Map Wipe?": true,
    "Chat Prefix": "<color=#e67e22>[EasyVote]</color> ",
    "Disable /vote command": false,
    "Command Cooldown Enabled?": true,
    "Command Cooldown Time (seconds)": 10.0
  },
  "Notification Settings": {
    "Globally announcment in chat when player voted (true / false)": true,
    "Enable the 'Please Wait' message when checking voting status?": true,
    "Notify player of rewards when they stop sleeping?": false,
    "Notify player of rewards when they connect to the server?": true,
    "If the player needs to vote, what should the single message in chat say?": "Hey, vote for our shit damn it. Type /note to get the links.",
    "Send only one message when /vote is called": false,
    "Notify player of already claimed rewards, try again message, on vote check?": true
  },
  "Note Settings": {
    "Enable give a Note to players on /vote?": true,
    "Title of the Note given to players on /vote": "Vote for us here!",
    "Content of the Note given to players on /vote": "A link to all your voting sites!"
  },
  "Simple Status Settings": {
    "Simple Status Enabled?": false,
    "Claim Rewards Settings": {
      "Banner Color (Decimal RGBA)": "0.18 0.8 0.44 1",
      "Icon Color (Decimal RGBA)": "0.93 0.94 0.95 1",
      "Main Text Color (Decimal RGBA)": "0.93 0.94 0.95 1",
      "Sub-Text Color (Decimal RGBA)": "0.93 0.94 0.95 1",
      "Icon (URL)": "https://i.imgur.com/bkoPUv4.png",
      "Main Text": "Claim Your Rewards!",
      "Sub-Text": "/claim",
      "Duration to show message": 10
    },
    "Needs To Vote Settings": {
      "Banner Color (Decimal RGBA)": "0.91 0.3 0.24 1",
      "Icon Color (Decimal RGBA)": "0.93 0.94 0.95 1",
      "Main Text Color (Decimal RGBA)": "0.93 0.94 0.95 1",
      "Sub-Text Color (Decimal RGBA)": "0.93 0.94 0.95 1",
      "Icon (URL)": "https://i.imgur.com/XVdKgGf.png",
      "Main Text": "Vote For Us!",
      "Sub-Text": "/vote",
      "Duration to show message": 10
    }
  },
  "Notify / UI Notify Settings": {
    "UINotify/Notify Enabled?": false,
    "Message to show when a player has unclaimed rewards": "You have unclaimed rewards! Type /claim now!",
    "Type of message to show when a player has unclaimed rewards": 0,
    "Message to show when a player needs to vote": "Support our server by voting! Type /vote now!",
    "Type of message to show when a player needs to vote": 1
  },
  "Toastify Settings": {
    "Toastify Enabled?": false,
    "Message to show when a player has unclaimed rewards": "You have unclaimed rewards! Type /claim now!",
    "Type of message to show when a player has unclaimed rewards": "error",
    "Unclaimed Message Duration": 10,
    "Message to show when a player needs to vote": "Support our server by voting! Type /vote now!",
    "Type of message to show when a player needs to vote": "success",
    "Needs to Vote Message Duration": 10
  },
  "Discord Settings": {
    "DiscordMessage Enabled (true / false)": false,
    "Discord Webhook (URL)": "https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks",
    "Discord Embed Title": "A player has just voted for us!",
    "Discord Embed Color (Integer String)": 3329330,
    "Notify @here when webhook is executed?": true,
    "Notify @everyone when webhook is executed?": false,
    "Some additional message to put inside of Discord embed": "Don't forget to vote! Type /vote in game chat to get started!"
  },
  "Reward Settings": {
    "Random Rewards": {
      "Random Rewards Enabled?": false,
      "Number of rewards to give from random rewards list": 1,
      "Rewards List": [
        "first command",
        "second command"
      ]
    },
    "Normal Rewards": {
      "Normal Rewards Enabled?": true,
      "Rewards List": {
        "@": [
          "first command",
          "second command"
        ],
        "@2": [
          "first command",
          "second command"
        ],
        "first": [
          "first command",
          "second command"
        ],
        "3": [
          "first command",
          "second command"
        ],
        "6": [
          "first command",
          "second command"
        ]
      }
    }
  },
  "Reward Descriptions": {
    "random": "Random Reward Description",
    "@": "Every Reward Description",
    "@2": "Every 2nd Reward Description",
    "first": "First Reward Description",
    "3": "Reward Description for the 3rd vote",
    "6": "Reward Description for the 6th vote"
  },
  "Server Vote Site ID/Keys": {
    "FirstServerName": {
      "GamesFinder.net": "ID:KEY",
      "Rust-Servers.net": "ID:KEY",
      "Rustservers.gg": "ID:KEY",
      "BestServers.com": "ID:KEY",
      "Top-Games.net": "ID:KEY",
      "TrackyServer.com": "ID:KEY"
    }
  },
  "DO NOT CHANGE! ---- API INFORMATION --- DO NOT CHANGE!": {
    "Rust-Servers.net": {
      "API Claim Reward (GET URL)": "http://rust-servers.net/api/?action=custom&object=plugin&element=reward&key={0}&steamid={1}",
      "API Vote status (GET URL)": "http://rust-servers.net/api/?object=votes&element=claim&key={0}&steamid={1}",
      "Vote link (URL)": "http://rust-servers.net/server/{0}",
      "Site Uses Username Instead of Player Steam ID?": false
    },
    "GamesFinder.net": {
      "API Claim Reward (GET URL)": "https://www.gamesfinder.net/api/vote?mode=claim&key={0}&steamid={1}",
      "API Vote status (GET URL)": "https://www.gamesfinder.net/api/vote?key={0}&steamid={1}",
      "Vote link (URL)": "https://www.gamesfinder.net/server/{0}",
      "Site Uses Username Instead of Player Steam ID?": false
    },
    "Rustservers.gg": {
      "API Claim Reward (GET URL)": "https://rustservers.gg/vote-api.php?action=claim&key={0}&server={2}&steamid={1}",
      "API Vote status (GET URL)": "https://rustservers.gg/vote-api.php?action=status&key={0}&server={2}&steamid={1}",
      "Vote link (URL)": "https://rustservers.gg/server/{0}",
      "Site Uses Username Instead of Player Steam ID?": false
    },
    "BestServers.com": {
      "API Claim Reward (GET URL)": "https://bestservers.com/api/vote.php?action=claim&key={0}&steamid={1}",
      "API Vote status (GET URL)": "https://bestservers.com/api/vote.php?action=status&key={0}&steamid={1}",
      "Vote link (URL)": "https://bestservers.com/server/{0}",
      "Site Uses Username Instead of Player Steam ID?": false
    },
    "Top-Games.net": {
      "API Claim Reward (GET URL)": "https://api.top-games.net/v1/votes/claim-username?server_token={0}&playername={1}",
      "API Vote status (GET URL)": "https://api.top-games.net/v1/votes/check?server_token={0}&playername={1}",
      "Vote link (URL)": "https://top-games.net/rust/{0}",
      "Site Uses Username Instead of Player Steam ID?": true
    },
    "TrackyServer.com": {
      "API Claim Reward (GET URL)": "https://api.trackyserver.com/vote/?action=claim&key={0}&steamid={1}",
      "API Vote status (GET URL)": "https://api.trackyserver.com/vote/?action=status&key={0}&steamid={1}",
      "Vote link (URL)": "https://trackyserver.com/server/{0}",
      "Site Uses Username Instead of Player Steam ID?": false
    }
  },
  "Version": {
    "Major": 4,
    "Minor": 0,
    "Patch": 14
  }
}
```



## Server ID's and Keys

Each voting website has a different way of getting your ID's and Keys. Some ID's are not used, but rather the slug in the URL is used instead.

For RustServers.gg, Rust-Servers.net, and BestServers.com you can find the id from the last part of the voting site's URL for your server.

RustServers.gg id is right here https://rustservers.gg/server/123 <- in this case, is 123

Rust-Servers.net, id is right here http://rust-servers.net/server/123 <- in this case, is 123

BestServers.com, id is right here http://BestServers.com/server/123 <- in this case, is 123

GamesFinder.net ID is right here https://www.gamesfinder.net/server/91 <- In this case, the ID is 91

For TrackyServer.com, and Top-Games.net, you can find the ID of your server in your URL as well, though it will not be a simple integer. It will have letters, numbers, and possibly dashes. You can view the screenshots attached in the download for more information. The highlighted portion of the URL will be your ID.

Key is secret key what you should not share any one. Key is hidden in the voting site dashboard. Login your account and navigate to modify your server, somewhere there should be your apikey, key, secret token, etc.

Note that you can add all your servers in this config and let player vote all your server. It also let players claim reward in any server.

You must reload the plugin after making changes to the config. If you found out that you do not get any reward after voting server or /vote chat command not showing any server what you just added. Then open logs (logs/EasyVotePro) and there you can see what cause the error. You can also enable debug mode and you can then reach out in the Support tab with your issue. If everything works just fine then start modifying rewards settings.

You can add multiple servers in the server id and keys section. Heres an example:

```
"Server Vote Site ID/Keys": {
    "FirstServerName": {
      "GamesFinder.net": "ID:KEY",
      "Rust-Servers.net": "ID:KEY",
      "Rustservers.gg": "ID:KEY",
      "BestServers.com": "ID:KEY",
      "Top-Games.net": "ID:KEY",
      "TrackyServer.com": "ID:KEY"
    },
    "SecondServerName": {
      "GamesFinder.net": "ID:KEY",
      "Rust-Servers.net": "ID:KEY",
      "Rustservers.gg": "ID:KEY",
      "BestServers.com": "ID:KEY",
      "Top-Games.net": "ID:KEY",
      "TrackyServer.com": "ID:KEY"
    },
    "ThirdServerName": {
      "GamesFinder.net": "ID:KEY",
      "Rust-Servers.net": "ID:KEY",
      "Rustservers.gg": "ID:KEY",
      "BestServers.com": "ID:KEY",
      "Top-Games.net": "ID:KEY",
      "TrackyServer.com": "ID:KEY"
    }
  }
```



## Simple Status Settings

In order to use the SimpleStatus, you must download the plugin here: https://codefling.com/plugins/simple-status

Just put that plugin into your Plugins folder, and enable the "Simple Status Enabled?" to "true".

The colors are in Normalized RGBA values.

You can use any icon that you want, however if you want the icon color to work correctly use an image/icon that is 100% white.

## UINotify/Notify Settings

In order to use the UINotify settings, you must download the plugin here: https://umod.org/plugins/ui-notify or https://codefling.com/plugins/notify

Do not forget to set the uinotify.see permission on your default user group!

## Discord Embeds

In order to use the Discord Embeds for when a player votes, you must download the DiscordMessages plugin from here: https://umod.org/plugins/discord-messages

A thing to note about the Discord Embeds... You must use a integer value for the embed color. To do the conversion, you can use an external tool like this one here: https://www.mathsisfun.com/hexadecimal-decimal-colors.html

## Rewards System - Normal vs. Random

The rewards system has been completely rewritten in the newest version of EasyVotePro. This rewards system has two options, random rewards and normal rewards. Normal rewards are just that. They execute based on the number of votes the player has. Random rewards choose from the list, and gives the number of rewards you set for each vote that the player gives. You must choose one system or the other. You can not use both at the same time.

The normal rewards have a structure to them.

The @ symbol means "every", so the @ entry is every vote.

@2 means every second vote. @3 means every third vote. Etc. etc. The numerical value is calculated using the following formula, and the player is only given those rewards if the remainder of the calculation is 0.

CurrentPlayerVoteCount % NumberAfter@Symbol == 0
The "first" entry can now be deleted out of the config if you don't want to give a reward to first time voters. First basically means that when a player first votes. Pretty self-explanatory. If you reset the players votes, either manually, or on a new map save, the player for their first vote of "the wipe" will get that reward.

The numerical values by themselves represent the exact vote count. So if you see in the default config 3 and 6, on the 3rd vote they're going to get those reward(s) or on the 6th vote they're going to get those reward(s).

All rewards are run as raw commands. So for instance, if you have the give plugin installed, you can use the giveto console command right in the reward list.

Use the below replacement variables when creating your rewards.

`{username}` -- player's display name
`{steamID}` -- player's Steam ID

## Testing Your Rewards

You can test out if your rewards are correct by enabling verbose debug mode. You have to enable both verbose and normal debug mode for this to work.

Each voting site has three values that it returns to tell the plugin whether or not a player has voted. Here's a breakdown of those values and what they mean.

0 - Player has not voted at all
1 (When checking a vote) - Player has voted
1 (When claiming a vote) - Player has voted, and will now set the vote as claimed
2 - Player has voted and it has already been claimed

You can use these values to test your rewards by setting both values to 1 in the config. Do not forget to turn verbose debug mode off in a live production environment or else the player will get the reward no matter if they voted or not!

## Reward Descriptions

Reward descriptions can be set to whatever you want. They're run in order from top to bottom. If you have random rewards enabled, it will only output the value for the random entry in the config.

## API Information Section

Do NOT change anything in that section. Don't add anything either. You will break the plugin. Only the sites that I have added are able to be used.

