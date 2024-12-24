# RankAPIv3

`RankAPIv3` is an advanced API for managing player ranks in a Minecraft server. It includes features such as dynamic rank management, temporary ranks, playtime-based promotions, rank persistence, and integration with both configuration files and databases.

This API is designed for flexibility, allowing extensive customization for ranks and efficient management of rank-based features.

***

### **Key Features**

1. **Dynamic Rank Management**
   * Add, remove, and retrieve ranks dynamically.
   * Store ranks in both configuration files and databases.
2. **Temporary Ranks**
   * Assign ranks for a limited time.
   * Automatically remove expired temporary ranks.
3. **Playtime-Based Promotions**
   * Promote players based on their total playtime.
   * Customize playtime requirements for each rank.
4. **Rank Persistence**
   * Store player ranks per world in the database.
   * Retrieve ranks seamlessly for players across server restarts.
5. **Economy Integration**
   * Apply rank-based multipliers for economy payouts.
6. **Chat Customization**
   * Define rank-specific prefixes, suffixes, and chat colors.

***

### **Initialization**

#### **Singleton Pattern**

`RankAPIv3` uses a private constructor to enforce a singleton pattern:

```java
private RankAPIv3() {
    if (system.getConfigHandler().connection.get().getBoolean("database.enabled")) {
        loadRanks();
        loadRanksFromDatabase();
    } else {
        loadRanks();
    }
}
```

To initialize and access `RankAPIv3`:

```java
RankAPIv3 rankAPI = new RankAPIv3();
```

***

### **Rank Structure**

#### **Rank Class**

Each rank is represented by the `Rank` class with the following attributes:

* **Name**: The rank identifier.
* **Permission**: Permission string required for the rank.
* **Prefix**: Chat prefix.
* **Suffix**: Chat suffix.
* **Chat Color**: Default chat color.
* **Priority**: Determines rank hierarchy.
* **Playtime Required**: Minimum playtime required for promotion to the rank.
* **Economy Multiplier**: Multiplier applied for economy-based rewards.
* **Taxes Due**: Tax deadlines for the rank.
* **Taxes Amount**: Tax amounts for the rank.

#### **Example**

```java
Rank rank = new Rank("Rank1", "system.rank.1", "&6[Rank 1]", "&f", "&a", 10, 3600000, 1.5, 7, 500.0);
```

***

### **Public Methods**

#### **Rank Management**

**Add or Retrieve Ranks**

* Add new rank:

```java
rankAPI.saveRankToDatabase(rank);
```

* Get all ranks:

```java
Collection<Rank> ranks = rankAPI.getRanks();
```

**Temporary Ranks**

* Assign a temporary rank:

```java
rankAPI.assignTemporaryRank(player.getUniqueId(), "Rank1", TimeUnit.HOURS.toMillis(1));
```

* Remove a temporary rank:

```java
rankAPI.removeTemporaryRank(player.getUniqueId());
```

* Check for expired ranks:

```java
rankAPI.checkTemporaryRanks();
```

***

#### **Playtime Management**

**Add and Get Playtime**

* Add playtime:

```java
rankAPI.addPlaytime(player.getUniqueId(), TimeUnit.HOURS.toMillis(2));
```

* Retrieve playtime:

```java
long playtime = rankAPI.getPlaytimeFromDatabase(player.getUniqueId());
```

**Promote by Playtime**

Promote a player based on their playtime:

```java
rankAPI.promotePlayerByPlaytime(player.getUniqueId());
```

***

#### **Rank Persistence**

**Player Rank Management**

* Assign rank to a player:

```java
rankAPI.assignRank(player, rank);
```

* Save rank to a specific world:

```java
rankAPI.savePlayerRank(player, world.getName(), rank.getName());
```

* Retrieve rank from a specific world:

```java
String rankName = rankAPI.getRankFromDatabase(player, world.getName());
```

**Delete Player Rank**

```java
rankAPI.removePlayerRank(player, world.getName());
```

***

#### **Economy Integration**

**Get Economy Multiplier**

Retrieve the economy multiplier for a rank:

```java
double multiplier = rankAPI.getRankMultiplier("Rank1");
```

**Apply Rank-Based Payout**

```java
rankAPI.applyRankPayout(player, 1000.0); // Base payout is 1000.0
```

***

#### **Chat Customization**

**Get Chat Settings**

* Prefix:

```java
String prefix = rankAPI.getRankPrefix("Rank1");
```

* Suffix:

```java
String suffix = rankAPI.getRankSuffix("Rank1");
```

* Chat Color:

```java
String chatColor = rankAPI.getRankChatColor("Rank1");
```

**AFK Prefix**

```java
String afkPrefix = rankAPI.setAFKPrefix();
```

***

### **Configuration Example**

#### **Ranks Configuration**

```yaml
chat:
  rank:
    Rank1:
      permission: "system.rank.1"
      prefix: "&6[Rank 1]"
      suffix: "&f[Admin]"
      chatcolor: "&a"
      priority: 10
      playtimeRequired: 3600000 # 1 hour in milliseconds
      economyMultiplier: 1.5
      taxes:
        due: 7
        amount: 500.0
```

***

### **Error Handling**

#### **Missing Rank**

Logs a warning if a rank is missing during initialization:

```
[WARNING] Rank 'Rank1' does not exist.
```

#### **Database Errors**

Logs SQL exceptions during database operations:

```
[SEVERE] Error updating playtime for player <UUID>: <Error Message>
```

***

### **Advanced Usage**

#### **Promotions with Custom Criteria**

Use `Criteria` to define custom promotion conditions:

```java
Criteria criteria = player -> player.hasPlayedBefore();
rankAPI.promotePlayer(player, newRank, criteria);
```

***

### **Best Practices**

1. **Database and Configuration Sync**:
   * Use both `saveRankToDatabase` and `saveRankToConfig` to ensure consistency.
2. **Temporary Ranks**:
   * Regularly invoke `checkTemporaryRanks()` to clean up expired ranks.
3. **Playtime Promotions**:
   * Set realistic playtime thresholds to encourage player progression.
4. **Logging**:
   * Monitor server logs for potential issues with missing ranks or configuration errors.

***
