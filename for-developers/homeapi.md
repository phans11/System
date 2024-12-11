# HomeAPI

## Overview

The `HomeAPI` is a core component of the system plugin, providing functionality for managing player homes in a Minecraft server. It allows players to set, retrieve, teleport to, delete, list, and rename their homes. The API also handles database integration to ensure persistence.

***

### Initialization

#### Constructor

```java
public HomeAPI(DatabaseManager databaseManager)
```

* **Parameters:**
  * `databaseManager`: The database manager used to handle SQL connections.
* **Description:** Initializes the `HomeAPI` instance with the given database manager.

***

### Methods

#### setHome

```java
public void setHome(Player player, String homeName)
```

* **Description:** Sets a new home for a player at their current location.
* **Parameters:**
  * `player`: The player setting the home.
  * `homeName`: The name of the home.
* **Behavior:**
  * Checks the player's rank and their home limit.
  * Validates if a home with the same name already exists.
  * Saves the home to the database if all conditions are met.
* **Notifications:** Sends appropriate messages to the player if the operation succeeds or fails.

***

#### getHome

```java
public Location getHome(Player player, String homeName)
```

* **Description:** Retrieves the location of a specified home.
* **Parameters:**
  * `player`: The player requesting the home.
  * `homeName`: The name of the home.
* **Returns:**
  * The `Location` of the home if found, otherwise `null`.
* **Behavior:**
  * First checks the in-memory cache.
  * If not found, attempts to load the home from the database.

***

#### deleteHome

```java
public void deleteHome(Player player, String homeName)
```

* **Description:** Deletes a specified home for the player.
* **Parameters:**
  * `player`: The player deleting the home.
  * `homeName`: The name of the home to delete.
* **Behavior:**
  * Removes the home from memory and the database.
  * Sends appropriate notifications to the player.

***

#### teleportToHome

```java
public void teleportToHome(Player player, String homeName)
```

* **Description:** Teleports the player to a specified home.
* **Parameters:**
  * `player`: The player being teleported.
  * `homeName`: The name of the home.
* **Behavior:**
  * Fetches the home location and teleports the player if the home exists.
  * Sends success or error messages to the player.

***

#### listHomes

```java
public void listHomes(Player player)
```

* **Description:** Lists all homes for a player.
* **Parameters:**
  * `player`: The player requesting the list.
* **Behavior:**
  * Fetches homes from the database.
  * Sends a formatted list of homes to the player or notifies them if none exist.

***

#### renameHome

```java
public void renameHome(Player player, String oldName, String newName)
```

* **Description:** Renames an existing home for a player.
* **Parameters:**
  * `player`: The player renaming the home.
  * `oldName`: The current name of the home.
  * `newName`: The new name for the home.
* **Behavior:**
  * Updates the home name in the database.
  * Notifies the player of success or failure.

***

#### saveHomeToDatabase

```java
public void saveHomeToDatabase(UUID playerId, String homeName, Location location)
```

* **Description:** Saves a home to the database.
* **Parameters:**
  * `playerId`: The UUID of the player.
  * `homeName`: The name of the home.
  * `location`: The location of the home.
* **Behavior:**
  * Executes an SQL query to insert or update the home in the database.

***

#### getHomesFromDatabase

```java
public Map<String, Location> getHomesFromDatabase(UUID playerId)
```

* **Description:** Fetches all homes for a player from the database.
* **Parameters:**
  * `playerId`: The UUID of the player.
* **Returns:**
  * A map of home names to locations.
* **Behavior:**
  * Executes an SQL query to retrieve all homes for the player.

***

#### deleteHomeFromDatabase

```java
private void deleteHomeFromDatabase(UUID playerId, String homeName)
```

* **Description:** Deletes a home from the database.
* **Parameters:**
  * `playerId`: The UUID of the player.
  * `homeName`: The name of the home to delete.
* **Behavior:**
  * Executes an SQL query to remove the home.

***

#### loadHomeFromDatabase

```java
private void loadHomeFromDatabase(UUID playerId, String homeName)
```

* **Description:** Loads a specific home from the database into memory.
* **Parameters:**
  * `playerId`: The UUID of the player.
  * `homeName`: The name of the home.
* **Behavior:**
  * Queries the database for the home and caches the result.

***

#### getPlayersWithHomes

```java
public List<String> getPlayersWithHomes()
```

* **Description:** Retrieves a list of players who have at least one home.
* **Returns:**
  * A list of player names.
* **Behavior:**
  * Executes an SQL query to find distinct players with homes.

***

#### getHomeNames

```java
public List<String> getHomeNames(UUID playerId)
```

* **Description:** Retrieves the names of all homes for a specific player.
* **Parameters:**
  * `playerId`: The UUID of the player.
* **Returns:**
  * A list of home names.
* **Behavior:**
  * Executes an SQL query to fetch home names for the player.

***

### Error Handling

* SQL errors are logged to the server console.
* Player-facing errors are displayed using the `PlaceholderHandler`.

***

### Dependencies

* `System` plugin for rank and database management.
* `PlaceholderHandler` for messaging.
* `DatabaseManager` for SQL operations.

***

### Notes

* The API uses a caching mechanism to reduce database queries.
* Homes are stored persistently in a database.
* Home limits are enforced based on player rank.
