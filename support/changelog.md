# Changelog

## 0.4.5.4-dev - 02/18/2021

### New

* **updated api-version to 1.16**
  * since System v0.4.5.4-dev \(this update\) System Dev-Version only supports Spigot 1.16.x - commands may not work in diffrent versions - i'll try my best, to support more Spigot Versions in the future
* **added kick option to AFK**
  * you can now enable if players should be kicked from server after a custom time period
* **added new Commands:**
  * /burn &lt;player&gt; &lt;duration&gt; - Burn other players
    * Permission:
      * system.admin - to receive all system rights
      * system.burn - allow players to burn others
  * /spawn &lt;create&gt; - Set a custom spawn location
    * Permission:
      * system.admin - to receive all system commands
      * system.spawn - allow players to teleport to spawn
      * system.spawn.create - allow players to create a spawn
* **/settings**
  * added function to reload item in system tab
  * added function to about item in system tab
  * added function to plugins item in system tab
  * added new permissions to allow players to open diffrent tabs
    * Permissions:
      * system.admin - to receive all system rights
      * system.settings.tab.server - to open server tab
      * system.settings.tab.world - to open world tab
      * system.settings.tab.player - to open player tab
      * system.settings.tab.system - to open system tab
      * system.settings.tab.staff - to open staff tab

### Removed

* removed output for /system plugins
* removed teleport command
* removed teleport command from config
* deprecated ItemBuilderV2
* deprecated InventoryBuilder
* **SystemAPI**
  * deprecated SystemAPI\#chat
  * deprecated SystemAPI\#placeholders
  * deprecated SystemAPI\#sendUsage
* **SettingsAPI**
  * deprecated SettingsAPI\#getInventoryFile
  * deprecated SettingsAPI\#getMessageFile
  * deprecated SettingsAPI\#getConfigFile
  * deprecated SettingsAPI\#ConnectionFile
* removed some unused config strings
* removed some unused permissions
* removed some unused permissions in config file

### 

### **Improvements**

* fixed issue that blocks the blacklist from blacklist upper case words in chat
* added whitespace to /broadcast for a better visability
* added option to change the gamemode in build command after you enable or disabled it
* heal command now adds exhaustion
* Invsee inventorys and enderchests have now custom inventory names - you can change these in the config
* toggle function in private chat is now customizeable
* added all new commands to /system help
* fixed command block could be removed from plugins gui
* fixed head command to support the new api-version
* fixed teamspeak info output - change config strings and added missing config string
* added usage messages to commands and made them customizeable

## 0.4.5.3-dev - 12/25/2020

### **New**

* **added Blacklist**
  * /blacklist &lt;add / remove / list&gt; &lt;name / word&gt;
    * system.blacklist.name
    * system.blacklist.name.add - add names only
    * system.blacklist.name.remove - remove names only
    * system.blacklist.name.list - list names only
    * system.blacklist.word
    * system.blacklist.word.add - add words only
    * system.blacklist.word.remove - remove words only
    * system.blacklist.word.list - list words only
  * block players with fraudlent names to join your server
  * censor messages with bad content
  * added support for Blacklist to Chatsystem and Joinsystem
* **new AFK detection**
  * players moving around, chatting, placing or removing blocks, or fishing, are no longer shown as afk
* **added possibility to disable private messages**
  * /msg toggle

### **Removed**

* temporary removed Teleport command
* removed Vault from softdepend - will be readded later on
* removed EconomySupport - will be readded later on
* removed VaultHook - will be readded later on
* removed SystemUpdater
* removed \#getPrefix\_Updater
* removed \#getSQLHandler - will be readded later on

### **Improvements**

* changed Package decleration from de.ypgames to de.isolveproblems
* changed plugin author from YPGames to isolveproblems
* fixed error output from time command
* fixed error output from SystemPlayer
* fixed chat formatting for players with no rank
* fixed some command do not work
* changed some string names in YouTube Command
* fixed typo in feed command permission
* **JoinSystem**
  * added support for ColorCodes to PremiumChat
  * added support for custom messages to PremiumChat
  * added support for ColorCodes to DisabledChat
  * added support for custom messages to DisabledChat
  * fixed \#setFoodLevel and \#setHealth function to work correctly
* **Settings**
  * added better handling for GUIs
  * added BackButtonHandler
  * added CloseButtonHandler
* **System**
  * added support for custom messages to reload command
  * added description and aliases to all commands
  * added all commands in to /system help
  * added \#getPrefix\_Broadcast
  * added \#getHomeAPI
  * added \#getSystemPlayer
  * added \#getTitle
* **SettingsAPI**
  * added \#isOnline
  * added \#getMaxPlayerCount
  * added \#randomInt
  * changed \#getCurrentPlayers to \#getCurrentPlayerCount



