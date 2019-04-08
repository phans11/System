System | Overhall Update

Features:

- More than 25+ Commands
- Permission Packages
- Join and Quit System
- Fully customizeable
- Customizeable Permissions
- En- or Disable Features you don't want to use
- Easy to use
- Easy to understand

Commands:

/system
Permission
system.admin - For all "System"-Commands
system.system - For the /system command
/system reload
Permission
system.reload
/system info
Permission
- none -
/system plugins
Permission
system.plugins
/system settings
Permission
system.settings
/system preversion
Permission
- none -
/afk
Permission
system.afk
/build
Permission
system.build
/chatclear (alias: /cc)
Permission
system.chatclear
CHANGED! ➥ /discord (alias: /dc)
Permission
system.social
system.discord
/teamspeak (alias: /ts)
Permission
system.social
system.teamspeak
/youtube (alias: /ytber or /yt)
Permission
system.social
system.youtube
/enchant (alias: /enc)
Permission
system.enchant
/enderchest (alias: ec)
Permission
system.enderchest
/workbench (alias: /wb)
Permission
system.workbench
/invsee <enderchest> <player>
Permission
system.invsee
system.invsee.inventory
system.invsee.enderchest
CHANGED! ➥ /time <day | night>
Permission
system.time
system.time.day
system.time.night
CHANGED! ➥ /weather <sun | rain | thunder>
Permission
system.weather
system.weather.sun
system.weather.rain
system.weather.thunder
/vote
Permission
system.vote
/msg <player>
Permission
system.msg
/fly <player>
Permission
system.fly
system.fly.self
system.fly.other
/gm  <player> <1 | 2 | 3 | 4> (alias: /gamemode)
Permission
system.gamemode
system.gamemode.self
system.gamemode.other
/heal <player>
Permission
system.heal
system.heal.self
system.heal.other
/kill <player>
Permission
system.kill
system.kill.self
system.kill.other
/ping
Permission
system.ping
/repair <all>
Permission
system.repair
system.repair.item
system.repair.all
NEW! ➥ /feed <player>
Permission
system.feed
system.feed.self
system.feed.other
NEW! ➥ /back
Permission
system.back
NEW! ➥ /skull <player> (alias: /head)
Permission
system.skull
___

Placeholder for all commands (Unless otherwise stated):
➥ %sender% - To get the sender of a command
➥ %player% - to get the player which send a command
➥ %target% - to get the targeted player of a command
➥ %prefix% - to get the prefix of 'System'

Placeholder for /back
➥ %prefix% - to get the prefix of 'System'
➥ %player% - to get the player which send a command
➥ %position_x% - to get the x position
➥ %position_y% - to get the y position
➥ %position_z% - to get the z position

Placeholder for /time
➥ %prefix% - to get the prefix of 'System'
➥ %sender% - To get the sender of a command
➥ %player% - to get the player which send a command
➥ %target% - to get the targeted player of a command[/COLOR]
➥ %time% - to get the ticks you've set the time to

Placeholder for /head
➥ %prefix% - to get the prefix of 'System'
➥ %player% - to get the player which send a command
➥ %target% - to get the targeted player of a command
➥ %uuid% - to get the uuid of the player

___

Config's
refix:
  system: "&eSystem &8\xbb"
  msg: "&5MSG &8\xbb"
error:
  permission: '%prefix% &cDu hast nicht die benoetigten Rechte, um diesen Command
    auszufuehren!'
  console: '%prefix% &cDu musst ein Spieler sein, um diesen Command ausfuehren zu
    koennen!'
  offline: '%prefix% &c Dieser Spieler ist aktuell nicht Online!'
system:
  admin:
    permission: system.admin
  reload:
    permission: system.reload
    message: '%prefix% &cDie config.yml wurde neugeladen!'
  commands:
    permission: system.system
  update:
    check: true
  death:
    message: '%prefix% &fDer Spieler &c%player% &fist gestorben!'
command:
  enable:
    player:
      afk: true
      back: true
      feed: true
      fly: true
      gamemode: true
      skull: true
      heal: true
      kick: true
      kill: true
      repair: true
      teleport: true
      vanish: true
      workbench: true
    ui:
      invsee: true
      vote: true
      enderchest: true
      enchant: true
    world:
      build: false
      time: true
      weather: true
    chat:
      msg: true
      clear: true
    social:
      discord: true
      teamspeak: true
      youtube: true
    connection:
      join:
        fake: true
      ping: true
listener:
  system:
    auto:
      complete: true
    death:
      enable: true
  ui:
    sign:
      change:
        enable: true
  chat:
    system:
      enable: true
  connection:
    join:
      enable: true
    quit:
      enable: true
      
messages:
  connection:
    enable: true
    teamspeak:
      info:
        title:
          header: '&e-=- UNSER TEAMSPEAK SERVER -=-'
          footer: '&e-=- UNSER TEAMSPEAK SERVER -=-'
        name: '&cName: '
        is_online: '&cOnline: '
        clients: '&cClients: '
    chatevent:
      rang:
        '1':
          permission: system.rang.1
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '2':
          permission: system.rang.2
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '3':
          permission: system.rang.3
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '4':
          permission: system.rang.4
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '5':
          permission: system.rang.5
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '6':
          permission: system.rang.6
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '7':
          permission: system.rang.7
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '8':
          permission: system.rang.8
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '9':
          permission: system.rang.9
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
      extra:
        '1':
          permission: system.extra.1
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '2':
          permission: system.extra.2
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '3':
          permission: system.extra.3
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '4':
          permission: system.extra.4
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'
        '5':
          permission: system.extra.5
          join: '&eDer Spieler &f%player% &ehat den Server betreten!'
          quit: '&eDer Spieler &f%player% &ehat den Server verlassen!'

messages:
  player:
    afk:
      permission: system.afk
      'on': '%prefix% &cDer Spieler %player% ist nun AFK'
      'off': '%prefix% &aDer Spieler %player% ist nicht mehr AFK'
    heal:
      permission: system.heal
      self:
        permission: system.heal.self
        message: '%prefix% &eDu hast dich geheilt!'
      other:
        permission: system.heal.other
        message_1: '%prefix% &eDer Spieler &7%target% &ewurde erfolgreich geheilt'
        message_2: '%prefix% &eDu wurdest von &7%player% &egeheilt'
    kill:
      permission: system.kill
      self:
        permission: system.kill.self
        message: '%prefix% &cDu wurdest getoetet!'
      other:
        permission: system.kill.other
        message_1: '%prefix% &eDu hast den Spieler &7%target% &egetoetet!'
        message_2: '%prefix% &cDu wurdest von &e%player% &cgetoetet!'
    back:
      permission: system.back
      message: '%prefix% &bDu wurdest erfolgreich zu deiner letzten gespeicherten
        Position teleportiert! (%position_X%, %position_Y%, %position_Z%)'
      file:
        saved: '%prefix% &aDein aktueller Standort wurde erfolgreich fuer eine Minute
          gepeichert!'
        deleted: '%prefix% &cDie Position deines letzen gepeicherten Standortes, wurde
          geloescht!'
    feed:
      permission: system.feed
      self:
        permission: system.feed.self
        message: '%prefix% &eDu hast dich gefuettert!'
      other:
        permission: system.feed.other
        message_1: '%prefix% &eDer Spieler &7%target% &ewurde erfolgreich gefuettert!'
        message_2: '%prefix% &eDu wurdest von %player% gefuettert!'
    fly:
      permission: system.fly
      self:
        permission: system.fly.self
        unavailable: '&cDu bist in einem Spielmodus, der das Fliegen nicht unterstuetzt!'
        activate:
          message: '%prefix% &eDu hast den Flugmodus &aaktiviert'
        deactivate:
          message: '%prefix% &eDu hast den Flugmodus &cdeaktiviert'
      other:
        permission: system.fly.other
        activate:
          message_1: '%prefix% &eDu hast den Spieler %target% erfolgreich in den Flugmodus
            gesetzt!'
          message_2: '''%prefix% &eDir wurde von %sender% der Flugmodus aktiviert'
        deactivate:
          message_1: '%prefix% &eDu hast den Spieler %target% erfolgreich aus dem
            Flugmodus entfernt!'
          message_2: '%prefix% &eDir wurde von %player% der Flugmodus deaktiviert'
    gamemode:
      permission: system.gamemode
      self:
        permission: system.gamemode.self
        survival: '%prefix% &6Dein Spielmodus ist nun: &cUeberleben'
        creative: '%prefix% &6Dein Spielmodus ist nun: &cKreativ'
        adventure: '%prefix% &6Dein Spielmodus ist nun: &cAbenteuer'
        spectator: '%prefix% &6Dein Spielmodus ist nun: &cZuschauer'
      other:
        permission: system.gamemode.other
        survival:
          message_1: '&eDer Spieler &6%target% &eist nun im Spielmodus: &cUeberleben'
          message_2: '&eDer Spieler &6%player% &ehat dich in den Ueberleben-Modus
            gesetzt!'
        creative:
          message_1: '&eDer Spieler &6%target% &eist nun im Spielmodus: &cKreativ'
          message_2: '&eDer Spieler &6%player% &ehat dich in den Kreativ-Modus gesetzt!'
        adventure:
          message_1: '&eDer Spieler &6%target% &eist nun im Spielmodus: &cAbenteuer'
          message_2: '&eDer Spieler &6%player% &ehat dich in den Abenteuer-Modus gesetzt!'
        spectator:
          message_1: '&eDer Spieler &6%target% &eist nun im Spielmodus: &cZuschauer'
          message_2: '&eDer Spieler &6%player% &ehat dich in den Zuschauer-Modus gesetzt!'
    repair:
      permission: system.repair
      item:
        permission: system.repair.item
        message: '%prefix% &aDas Item in deiner Hand wurde repariert!'
      all:
        permission: system.repair.all
        message: '%prefix% &aAlle Items in deinem Inventar wurden repariert!'
    vanish:
      permission: system.vanish
      activate:
        message: '%prefix% &aDu bist nun unsichtbar!'
      deactivate:
        message: '%prefix% &cDu bist nun nicht mehr unsichtbar!'
  world:
    build:
      permission: system.build
      activate:
        title:
          line:
            '1': '&cBaumodus'
            '2': '&awurde aktiviert!'
        message:
          self: '%prefix% &cDu befindest dich nun im Baumodus'
          all: '%prefix% &cDer Spieler &e%player% &cbefindet sich nun im Baumodus'
      deactivate:
        title:
          line:
            '1': '&cBaumodus'
            '2': '&awurde deaktiviert!'
        message:
          self: '%prefix% &aDu befindest dich nun nicht mehr im Baumodus'
          all: '%prefix% &aDer Spieler &e%player% &abefindet sich nun nicht mehr im
            Baumodus'
    time:
      permission: system.time
      day:
        permission: system.time.day
        ticks: 350
        message: '%prefix% &eDu hast die Tageszeit zu &aTag (%time%) &egeaendert'
      night:
        permission: system.time.night
        ticks: 13000
        message: '%prefix% &eDu hast die Tageszeit zu &cNacht (%time%) &egeaendert'
      usage: '%prefix% &cBitte verwende /time <day | night>'
    weather:
      permission: system.weather
      sun:
        permission: system.weather.sun
        message: '%prefix% &eDas Wetter ist nun: &cSonnig'
      rain:
        permission: system.weather.rain
        message: '%prefix% &eDas Wetter ist nun: &cRegnerisch'
      thunder:
        permission: system.weather.thunder
        message: '%prefix% &eDas Wetter ist nun: &cStuermig'
  chat:
    clear:
      permission: system.chat.clear
      count: 200
      message: '%prefix% &cDer Chat wurde von &6%player% &cgeleert!'
    msg:
      permission: system.msg
  ui:
    workbench:
      permission: system.workbench
      message: '%prefix% &eDu hast die Werkbank geoeffnet!'
    enchant:
      permission: system.enchant
      usage: '%prefix% &cBitte verwende: /enchant'
      message: '%prefix% &eDu kannst nun dein Gegenstand verzaubern!'
    enderchest:
      permission: system.enderchest
      message: '%prefix% &eDu hast deine Enderchest geoeffnet!'
    invsee:
      permission: system.invsee
      inventory:
        permission: system.invsee.inventory
        usage: '%prefix% &cBitte verwende /invsee <enderchest> <player>'
        message: '%prefix% &eDu hast das Inventar von &c %target% &egeoeffnet!'
        error:
          own_inventory: '%prefix% &cDu kannst dein eigenes Inventar nicht durch diesen
            Command ansehen!'
          offline: '%prefix% &cDieser Spieler ist nicht online!'
      enderchest:
        permission: system.invsee.enderchest
        message: '%prefix% &eDu hast die Enderchest von &c %target% &egeoeffnet!'
    head:
      usage: '&cUsage: /head <player>'
      item:
        name: '%prefix% &b%target%'
      lore:
        line:
          '1': '&eName&7: &b%target%'
          '2': '&eBekommen durch&7: &b%player%'
          '3': '&eUUID&7: &b%uuid%'
    vote:
      permission: system.vote
      link:
        '1':
          enable: true
          line:
            '1':
              enable: true
              message: '&eVOTE - Fuege deinen Text ein! - Vote-Link 1'
            '2':
              enable: true
              message: '&eVOTE - Fuege deinen Text ein! - Vote-Link 1'
            '3':
              enable: true
              message: '&eVOTE - Fuege deinen Text ein! - Vote-Link 1'
            '4':
              enable: true
              message: '&eVOTE - Fuege deinen Text ein! - Vote-Link 1'
            '5':
              enable: true
              message: '&eVOTE - Fuege deinen Text ein! - Vote-Link 1'
            '6':
              enable: true
              message: '&eVOTE - Fuege deinen Text ein! - Vote-Link 1'
        '2':
          enable: true
          line:
            '1':
              enable: true
              message: '&bVOTE - Fuege deinen Text ein! - Vote-Link 2'
            '2':
              enable: true
              message: '&bVOTE - Fuege deinen Text ein! - Vote-Link 2'
            '3':
              enable: true
              message: '&bVOTE - Fuege deinen Text ein! - Vote-Link 2'
            '4':
              enable: true
              message: '&bVOTE - Fuege deinen Text ein! - Vote-Link 2'
            '5':
              enable: true
              message: '&bVOTE - Fuege deinen Text ein! - Vote-Link 2'
            '6':
              enable: true
              message: '&bVOTE - Fuege deinen Text ein! - Vote-Link 2'
        '3':
          enable: true
          line:
            '1':
              enable: true
              message: '&aVOTE - Fuege deinen Text ein! - Vote-Link 3'
            '2':
              enable: true
              message: '&aVOTE - Fuege deinen Text ein! - Vote-Link 3'
            '3':
              enable: true
              message: '&aVOTE - Fuege deinen Text ein! - Vote-Link 3'
            '4':
              enable: true
              message: '&aVOTE - Fuege deinen Text ein! - Vote-Link 3'
            '5':
              enable: true
              message: '&aVOTE - Fuege deinen Text ein! - Vote-Link 3'
            '6':
              enable: true
              message: '&aVOTE - Fuege deinen Text ein! - Vote-Link 3'
  connection:
    ping:
      permission: system.ping
      message: "&eDein Ping &8\xbb &c"
  social:
    permission: system.social
    youtube:
      permission: system.youtube
      line:
        '1': ' '
        '2': '&e&l- Anforderungen &6&lPremium+-Rang &e&l-'
        '3': ' '
        '4': "&8\xbb &eMindestens &c500 &eAbonnenten und"
        '5': "&8\xbb &c5000 &eAufrufe im Monat"
        '6': ' '
        '7': '&e&l- Anforderungen &5&lYoutuber-Rang &e&l-'
        '8': ' '
        '9': "&8\xbb &eMindestens &c1000 &eAbonnenten und"
        '10': "&8\xbb &c10000 &eAufrufe im Monat"
        '11': ' '
    discord:
      permission: system.discord
      line:
        '1': ''
        '2': '&e- Unser &b&lDiscord-Server &e&l-'
        '3': ''
        '4': "&8\xbb &eHier findest du unseren"
        '5': "&8\xbb &eDiscord-Server: &cDein Joinlink"
        '6': ''
        '7': '&e- Unser &b&lDiscord-Server &e&l-'
        '8': ''
    teamspeak:
      permission: system.teamspeak
      line:
        '1': '  '
        '2': '&e- Unser &b&lTeamSpeak-Server &e&l-'
        '3': '  '
        '4': "&8\xbb &eHier findest du unseren"
        '5': "&8\xbb &eTeamSpeak-Server: &cDeine TeamSpeak-IP"
        '6': '  '
        '7': '&e- Unser &b&lTeamSpeak-Server &e&l-'
        '8': '  '

___
➥ System
system.admin - to have all permissions of system

Commands:
- All

➥ Social
system.social - to have all social command permissions of system like

Commands:
/youtube - /ytber - /yt
/discord - /dc
/teamspeak <info> - /ts <info>

➥ Weather
system.weather

Commands:
weather <sun / rain / thunder>

➥ Time
system.time

Commands:
/time <day / night>

➥ Heal
system.heal

Commands:
/heal <player>

➥ Feed
system.feed

Commands:
/feed <player>

➥ Kill
system.kill

Commands:
/kill <player>

➥ Fly
system.fly

Commands:
/fly <player>

➥ Gamemode
system.gamemode

Commands:
/gm 1 <player>

➥ Repair
system.repair

Commands:
/repair <all>

➥ Invsee
system.invsee

Commands:
/invsee <enderchest> <player>

With these permissions you can execute all command combinations you want!
Here is an example:

With the permission "system.weather", you can change the weather in all the types it can be, like Sun, Rain or Thunder.

With the permission "system.weather.sun" you can only change the weather to sun on the server.

With the permission "system.weather.rain" you can only change the weather to rain on the server.

With the permission "system.weather.thunder" you can only change the weather to thunder on the server


Developer-Area

➥ API - System

UUIDFetcher:

UUIDFetcher.getUUID(name); - To receive the uuid of an user


[*] Coming soon! - RoadMap
 
➥ [v.0.4.0 - Name: Overhall Update] - Released - 24.03.2019
    [+] More Commands [Currently: 2 Commands] [100%]
    [+] Permission-Packages [100%]
    [+] Easier usage of system [100%]
    [+] A new config to understand "System" easier [100%]
    [+] Better Code accessability [100% / 1/3]
    [+] Better performance of "System"

➥ [v.0.4.1 - Name: -]
    [+] More Commands [Currently: - Commands] [10%]
    [+] Some command changes (/msg and /ping) [30%]
    [+] New Reload-Command [10%]
    [+] Scoreboard [60%]
    [+] AutoAnnouncer [0%]
    [+] It's a secret - Stay tuned [2%]

NEW ➥ [v.2.0.Beta-0 Feature - Name: Back Home] - Work in Progress
    [+] Set / Delete / Change homepoints [0%]
    [+] Better Code accessability [0% / 2/3]
    [+] More Commands [Currently: 5 Commands] [1%]
 
➥ [v.2.0.Beta-1 Feature - Name: Stay Connected Update] - Not startet yet
    [+] Connect the System-Plugin to a Database (MySQL) [80%]
    [+] More Commands [Currently: 0 Commands] [0%]
    [+] More Commands [Currently: 0 Commands] [0%]
    [+] Better Code accessability [0% / 3/3]

➥ [v.2.0.Beta-2 Feature - Name: Getting Banned Update] - Not started yet
    [+] Ban/Kick System [0%]
    [+] Mute System [0%]
    [+] Addons for System
    [+] More Commands [Currently: 0 Commands] [0%]

➥ [v.2.0.Beta-3 Feature - Name: Unknown] - Not started yet
    [+] Language-System - Change the default language of System [5%]
    [+] reworked Config-System [0%]
    [+] More Commands [Currently: 0 Commands] [0%]
