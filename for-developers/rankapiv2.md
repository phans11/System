---
description: >-
  The RankAPI class is a utility designed for managing ranks in a Minecraft
  server. It includes features like rank prefixes, chat colors, player rank
  determination, timed ranking based on playtime, and
---

# RankAPIv2

### **Features**

* **Rank Management**
  * Define ranks with permissions and priorities.
  * Customize rank chat prefixes and colors via configuration.
* **Player Rank Handling**
  * Determine the highest rank of a player based on permissions.
  * Check if a player has a specific rank.
  * Retrieve playtime and rank-based limits.
* **Timed Ranking**
  * Add and retrieve playtime from the database.
  * Display formatted playtime to players.
  * Support for automatic rank upgrades based on playtime.
* **Session Management**
  * Track and manage player session start times.
* **Integration**
  * Support for configuration and database-based rank management.
  * Extensible for new ranks and features.

***

### **Initialization**

#### **Constructor**

```java
public RankAPI()
```

* Initializes the `RankAPI` instance by loading rank prefixes and chat colors from the configuration.

***

### **Enums**

#### **Rank**

Defines all available ranks and their properties:

* **Name**: Internal rank identifier.
* **Permission**: Permission string associated with the rank.
* **Priority**: Integer indicating rank priority (higher number = higher priority).

Example:

```java
Rank.RANK_1.getName(); // "rank.1"
Rank.RANK_1.getPermission(); // "system.rank.1"
Rank.RANK_1.getPriority(); // 13
```

***

### **Public Methods**

#### **Rank and Chat Management**

**`Set<String> getRanks()`**

Returns all available rank names.

**`String getRankChatPrefix(Rank rank)`**

Returns the chat prefix for the specified rank.

**`String getRankChatColor(Rank rank)`**

Returns the chat color for the specified rank.

**`Rank getPlayerRank(Player player)`**

Determines the highest rank of a player based on their permissions.

**`boolean isStaff(Rank rank)`**

Checks if a rank is designated as a staff rank.

**`boolean hasRank(Player player, Rank rank)`**

Checks if a player has the specified rank.

**`int getHomeLimit(RankAPIv3.Rank rank)`**

Returns the home creation limit for a specific rank.

***

#### **Timed Ranking**

**`void addPlaytime(UUID playerId, long playtimeMillis)`**

Adds playtime to a player's record in the database.

**`void displayPlaytime(CommandSender sender, UUID playerId, String playerName)`**

Sends the formatted playtime of a player to a command sender.

**`long getPlaytimeFromDatabase(UUID playerId)`**

Retrieves the total playtime of a player from the database.

**`String formatPlaytime(long millis)`**

Formats playtime in a human-readable format with localization support.

***

#### **Session Management**

**`void storeSessionStartTime(UUID playerUUID, long startTime)`**

Stores the session start time for a player in the database.

**`Long getSessionStartTime(UUID playerId)`**

Retrieves the session start time of a player.

**`void clearSessionStartTime(UUID playerId)`**

Clears the session start time of a player.

***

#### **Other Utilities**

**`String setAFKPrefix()`**

Retrieves the AFK prefix defined in the configuration.

**`String getSeparator()`**

Returns the separator used in the chat layout.

**`String getSplitter()`**

Returns the splitter used in the chat layout.

***

### **Configuration**

#### Example Configuration File

```yaml
chat:
  layout:
    splitter: "|"
    separator: "-"
    afk:
      prefix: "&7[AFK]"

  rank.1:
    prefix: "&6[Rank 1]"
    chatcolor: "&f"
    isStaff: false
  rank.2:
    prefix: "&e[Rank 2]"
    chatcolor: "&f"
    isStaff: true

homeSettings:
  homes:
    create:
      limit:
        rank:
          rank.1: 3
          rank.2: 5
```

***

### **Dependencies**

* **Configuration**: The API relies on a configuration file (`config.yml`) for prefixes, colors, and other rank-specific settings.
* **Database**: Playtime and session data are stored in a database using SQL queries.

***

### **Usage Examples**

#### Get Player's Rank

```java
Player player = Bukkit.getPlayer("examplePlayer");
RankAPI.Rank rank = rankAPI.getPlayerRank(player);
System.out.println("Player's rank: " + rank.getName());
```

#### Add Playtime

```java
UUID playerId = player.getUniqueId();
rankAPI.addPlaytime(playerId, 3600000); // Add 1 hour of playtime
```

#### Display Playtime

```java
rankAPI.displayPlaytime(sender, playerId, "examplePlayer");
```

***

### **Deprecated Notice**

This class is marked as deprecated and should be replaced with `RankAPIv3` for better performance and features.
