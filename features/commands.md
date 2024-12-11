---
description: All informations about the commands available with System
---

# Commands and Permissions

#### Plugin System Commands

Below is a summary of the Plugin System commands, their permissions, descriptions, and usage.

**Commands**

* **/system** \[alias: /s]
  * **Permission:** `system.help`
  * **Description:** List of all commands and there usage.
  * **Usage:** `/system`
* **/system reload**
  * **Permission:** `system.reload`
  * **Description:** Reload the configuration.
  * **Usage:** `/system reload`
* **/system plugins**
  * **Permission:** `system.plugins`
  * **Description:** List all installed plugins in a GUI.
  * **Usage:** `/system plugins`
*   **/system info**

    * **Permission:** `no permission`
    * **Description:** Informations about the Plugin.
    * **Usage:** `/system info`

    For further details on configurations and advanced usage, refer to the [System Dev Version documentation](https://www.spigotmc.org/resources/system-dev-version.66136/).
* **/afk**
  * **Permission:** `system.afk`
  * **Description:** Set your status to AFK
  * **Usage:** `/afk <on> <off>`
* **/build**
  * **Permission:** `system.build`
  * **Description:** Go into Build Mode.
  * **Usage:** `/build`
* **/blacklist**
  * **Permission:** `system.blacklist / system.blacklist.name / system.blacklist.name.add / system.blacklist.name.remove / system.blacklist.name.list / system.blacklist.word / system.blacklist.world.add / system.blacklist.word.remove / system.blacklist.word.list`
* **Description:** Blacklist names and prevent joining the  server or words within the chat.
* **Usage:** `/blacklist <add> <remove> <list> [name] [word] [blacklisted item]`
* **/broadcast**
  * **Permission:** `system.broadcast`
  * **Description:** Broadcast informations to all players.
  * **Usage:** `/broadcast {-sound} {-title} [message]`&#x20;
* **/chatclear** \[alias: /cc]
  * **Permission:** `no permission`
  * **Description:** Clear the howl chat, a player or yourself.
  * **Usage:** `/chatclear <player>`
* &#x20;**/discord** \[alias: /dc]
  * **Permission:** `system.discord`
  * **Description:** Details about your Discord Server.
  * **Usage:** `/discord`
* **/teamspeak** \[alias: /ts]
  * **Permission:** `system.teamspeak`
  * **Description:** Details about your Teamspeak Server.
  * **Usage:** `/teamspeak`
* **/youtube** \[alias: /yt]
  * **Permission:** `system.youtube`
  * **Description:** Details about your YouTube Account.
  * **Usage:** `/youtube`
* **/enderchest** \[alias: /ec]
  * **Permission:** `system.enderchest`
  * **Description:** Access your enderchest.
  * **Usage:** `/enderchest`
* **/workbench**\[alias: /wb]
  * **Permission:** `system.workbench`
  * **Description:** Open up a virtual workbench.
  * **Usage:** `/workbench`
* **/invsee**
  * **Permission:**  `system.invsee / system.invsee.inventory / system.invsee.enderchest`
  * **Description:** Look in a players inventory or enderchest.
  * **Usage:** `/invsee <enderchest> [player]`
* **/time**
  * **Permission:** `system.time / system.time.day / system.time.night / system.time.noon / system.time.sunset / system.time.sunrise / system.time.set / system.time.now`
  * **Description:** Set a different time for a specific world.
  * **Usage:** `/time <day> <night> <noon> <sunset> <sunrise> <now> <set> [0-24000]`
* **/weather**
  * **Permission:** `no system.weather / system.weather.sun / system.weather.rain / system.weather.thunder`
  * **Description:** Set a different weather for a specific world
  * **Usage:** `/weather <sun> <rain> <thunder>`
* **/vote**
  * **Permission:** `system.vote`
  * **Description:** Get vote links.
  * **Usage:** `/vote`
* **/msg** and **/reply** \[alias: /private]
  * **Permission:** `system.private / system.private.toggle`
  * **Description:** Clear the howl chat, a player or yourself.
  * **Usage:** `/msg <toggle> [player] [message] - /r`
* **/fly**
  * **Permission:** `system.fly / system.fly.self / system.fly.others`
  * **Description:** Set yourself or others into fly mode.
  * **Usage:** `/fly <player>`
* **/gamemode** \[alias: /gm]
  * **Permission:** `system.gamemode / system.gamemode.self / system.gamemode.others`
  * **Description:** Set yourself or others into different gamemodes.
  * **Usage:** `/gamemode <1> <2> <3> <4> or /gamemode <creative> <survival> <adventure> <spectator>`
* **/heal**
  * **Permission:** `system.heal / system.heal.self / system.heal.others`
  * **Description:** Heal yourself or other players.
  * **Usage:** `/heal <player>`
* **/feed**
  * **Permission:** `system.feed / system.feed.self / system.feed.others`
  * **Description:** Feed yourself or other players.
  * **Usage:** `/feed <player>`
* **/teleport**
  * **Permission:** `system.teleport / system.teleport.player / system.teleport.location`
  * **Description:** Teleport to players, locations or entities.
  * **Usage:** `/teleport <player> or /teleport <x> <y> <z> or /teleport <entity>`&#x20;
* **/kill**
  * **Permission:** `system.kill / system.self / system.kill.others`
  * **Description:** Kill yourself or others.
  * **Usage:** `/kill <player>`
* **/repair**
  * **Permission:** `system.repair / system.repair.item / system.repair.inventory / system.repair.tools`
  * **Description:** Repair an item in your hand, your howl inventory or only tools inside your inventory.
  * **Usage:** `/repair <inventory> <tools>`
* **/back**
  * **Permission:** `system.back`
  * **Description:** Save your current location and teleport back within x seconds.
  * **Usage:** `/back <save>`
* **/skull**
  * **Permission:** `system.skull`
  * **Description:** Receive a skull with skin if different players.
  * **Usage:** `/skull <player>`
* **/speed**
  * **Permission:** `system.speed / system.speed.fly / system.speed.walk`
  * **Description:** Set your walk or fly speed.
  * **Usage:** `/speed fly <1-5> or /speed walk <1-5>`
* **/spawn**
  * **Permission:** `system.spawn / system.spawn.create`
  * **Description:** Teleport to spawn or create a spawn.
  * **Usage:** `/spawn <create>`
* **/burn**
  * **Permission:** `system.burn`
  * **Description:** Burn yourself or a player.
  * **Usage:** `/burn <player> <duration>`
* **/tablist**
  * **Permission:** `system.tablist`
  * **Description:** Reload the PrefixSystem.
  * **Usage:** `/tablist reload`
* **/economy**
  * **Permission:** `system.economy.all / system.economy.deposit / system.economy.withdraw / system.economy.send / system.economy.balance / system.economy.balance.self / system.economy.balance.target / system.economy.toggle / system.economy.reset / system.economy.set`
  * **Description:** Access to the EconomySystem.
  * **Usage:** `/economy <balance> <player> or /economy <deposit> <withdraw> <set> <player> <amount> or /economy reset <player> or /economy balance <player>`&#x20;
* **/creator**
  * **Permission:** `system.creator`
  * **Description:** Details about the Creator Rank.
  * **Usage:** `/creator`
* **/twitch**
  * **Permission:** `system.twitch`
  * **Description:** Details about your Twitch Channel.
  * **Usage:** `/twitch`
* **/tiktok**
  * **Permission:** `system.kill / system.self / system.kill.others`
  * **Description:** Details about your TikTok Channel.
  * **Usage:** `/tiktok`
* **/website**
  * **Permission:** `system.website`
  * **Description:** Details about your website.
  * **Usage:** `/website`
* **/premium**
  * **Permission:** `system.premium`
  * **Description:** Details about the Premium Rank.
  * **Usage:** `/premium`
* **/stack**
  * **Permission:** `system.stack`
  * **Description:** Stack the item in your hand.
  * **Usage:** `/stack`
* **/shutdown**
  * **Permission:** `system.shutdown`
  * **Description:** Shutdown the server.
  * **Usage:** `/shutdown [duration]`
* **/extinguish**
  * **Permission:** `system.extinguish`
  * **Description:** Extinguish a player.
  * **Usage:** `/extinguish <player>`
* **/firework**
  * **Permission:** `system.firwork`
  * **Description:** Create a firework \[New Years Eve-Feature].
  * **Usage:** `/firework <duration> [style] <message>`
* **/smelt**
  * **Permission:** `system.smelt`
  * **Description:** Smelt the items in your hand or inventory.
  * **Usage:** `/smelt <all>`
