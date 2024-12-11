# ConfigAPI

### Overview

The `ConfigAPI` is a utility class designed to simplify the management of YAML configuration files in a Spigot plugin. It provides functionality for creating, loading, saving, and modifying configuration files, including player-specific configurations and inline comments.

***

### Initialization

#### Constructors

*   **`ConfigAPI(String path, String fileName, Plugin plugin)`**

    Creates or loads a configuration file at the specified path. If the file does not exist, it is created with default settings.

    **Parameters:**

    * `path` (String): The directory path where the configuration file is located.
    * `fileName` (String): The name of the configuration file.
    * `plugin` (Plugin): The plugin instance.
*   **`ConfigAPI(String path, String fileName, Runnable callback, Plugin plugin)`**

    Same as above, but with an additional callback that runs after creating a new configuration file.

    **Parameters:**

    * `path` (String): The directory path where the configuration file is located.
    * `fileName` (String): The name of the configuration file.
    * `callback` (Runnable): Code to execute after creating a new configuration file.
    * `plugin` (Plugin): The plugin instance.

***

### Static Methods

#### `getConig(String path, String fileName, Plugin plugin)`

Initializes and retrieves a singleton instance of the `ConfigAPI`. Subsequent calls return the existing instance.

**Parameters:**

* `path` (String): The configuration directory.
* `fileName` (String): The configuration file name.
* `plugin` (Plugin): The plugin instance.

**Returns:**

* `ConfigAPI`: The singleton instance of the class.

#### `getConfig()`

Retrieves the existing instance of `ConfigAPI`. Throws an exception if not initialized.

**Returns:**

* `ConfigAPI`: The singleton instance of the class.

**Throws:**

* `IllegalStateException`: If the `ConfigAPI` has not been initialized.

***

### Core Methods

#### File Management

* **`save()`**: Writes the in-memory configuration to the file, preserving inline comments.
* **`reloadConfig()`**: Reloads the configuration from the file.
*   **`exists()`**: Checks if the configuration file exists.

    **Returns:**

    * `boolean`: `true` if the file exists, `false` otherwise.
* **`delete()`**: Deletes the configuration file if it exists.

#### Access and Modification

* **`get()`**: Retrieves the `FileConfiguration` object for the main configuration file.
*   **`setInlineComments(String path, List<String> comments)`**: Adds inline comments for a specified configuration path.

    **Parameters:**

    * `path` (String): The configuration path.
    * `comments` (List): The list of comments to add.
* **`setStringList(String path, List<String> list)`**: Sets a list of strings at the specified path.
*   **`getStringList(String path)`**: Retrieves a list of strings from the specified path.

    **Returns:**

    * `List<String>`: The string list from the specified path.
* **`addDefaultStringList(String path, List<String> defaultList)`**: Sets a default string list if the path does not already exist.

#### Version Management

*   **`checkVersion(String currentVersion)`**: Logs a warning if the configuration version does not match the provided version.

    **Parameters:**

    * `currentVersion` (String): The expected version of the configuration.

***

### Player-Specific Configuration

#### Loading and Saving

*   **`getPlayerConfig(Player player)`**: Retrieves or creates a YAML configuration file for a specific player.

    **Parameters:**

    * `player` (Player): The player instance.

    **Returns:**

    * `YamlConfiguration`: The player's configuration file.
* **`saveModifiedConfigs()`**: Saves only the configurations marked as modified.
* **`setPlayerConfigModified(Player player)`**: Marks a player's configuration as modified for saving.

#### Access and Modification

*   **`setPlayerConfigValue(Player player, String path, Object value)`**: Sets a value in a player's configuration and marks it as modified.

    **Parameters:**

    * `player` (Player): The player instance.
    * `path` (String): The configuration path.
    * `value` (Object): The value to set.
*   **`getPlayerConfigValue(Player player, String path, T defaultValue)`**: Retrieves a value from a player's configuration with a fallback default.

    **Parameters:**

    * `player` (Player): The player instance.
    * `path` (String): The configuration path.
    * `defaultValue` (T): The default value to return if the path does not exist.

    **Returns:**

    * `T`: The retrieved value.

#### Locations

* **`setPlayerLocation(Player player, String path, Location location)`**: Stores a player's location in their configuration file.
*   **`getPlayerLocation(Player player, String path)`**: Retrieves a player's location from their configuration file.

    **Returns:**

    * `Location`: The retrieved location or `null` if not set.

***

### Location Management

* **`setLocation(String path, Location location)`**: Sets a location in the main configuration file.
*   **`getLocation(String path)`**: Retrieves a location from the main configuration file.

    **Returns:**

    * `Location`: The retrieved location or `null` if not set.

***

### Utility Methods

* **`checkVersion(String currentVersion)`**: Checks the configuration file's version against the provided version string. Logs a warning if they do not match.
* **`setStringList(String path, List<String> list)`**: Sets a list of strings in the configuration at the specified path.
* **`getStringList(String path)`**: Retrieves a list of strings from the configuration file.

***

### Notes

* Ensure `ConfigAPI` is initialized using `getConig` before calling other methods.
* Supports inline comments, player-specific configurations, and location handling for better organization and usability.
* Automatically creates missing files and directories when saving configurations.

***

### Examples

#### Initialize and Use

```java
// Initialize ConfigAPI
ConfigAPI configAPI = ConfigAPI.getConig("plugins/MyPlugin", "config.yml", plugin);

// Set and save a value
configAPI.get().set("example.path", "Hello World!");
configAPI.save();

// Retrieve a value
String value = configAPI.get().getString("example.path");
System.out.println(value);
```

#### Inline Comments

```java
// Add inline comments
configAPI.setInlineComments("example.path", Arrays.asList("This is an example", "Set to a greeting"));
```

#### Player-Specific Configuration

```java
// Set a player's configuration value
Player player = Bukkit.getPlayer("playerName");
configAPI.setPlayerConfigValue(player, "example.key", "value");

// Retrieve a value with a default
String playerValue = configAPI.getPlayerConfigValue(player, "example.key", "default");
System.out.println(playerValue);
```

#### Handling Locations

```java
// Save a location
Location loc = player.getLocation();
configAPI.setLocation("spawn", loc);

// Retrieve a location
Location spawnLoc = configAPI.getLocation("spawn");
player.teleport(spawnLoc);
```







## How to hook into ConfigAPI

{% code title="Configurations.java" lineNumbers="true" %}
```java
import de.isolveproblems.system.api.ConfigAPI;

public class ConfigurationMessages {

    private final YourProject yourProject = YourProject.getPlugin(YourProject.class);

    public ConfigAPI config;

    public void getConfig() {
        config = new ConfigAPI("plugins/YourProject", "config.yml", yourProject);
        config.getConfig().addDefault("config.prefix", "&c[YourProject]");
        config.saveConfig();
    }
}
```
{% endcode %}

## Configuration in Main Class

{% code lineNumbers="true" %}
```java
import de.isolveproblems.system.api.SettingsAPI;

public class YourProject extends JavaPlugin {

    private YourProject yourProject;
    private Configuration configHandler;

    @Override
    public void onEnable() {
        this.yourProject = this;
        this.configHandler= new ConfigurationHandler();
        
        this.load();
    }

    @Override
    public void onDisable() {

    }

    public YourProject getYourProject() {
        return this.yourProject;
    }
    
    public void load() {
        this.getConfiguration().getConfig();
    }
        
    public Configuration getConfiguration() {
        return this.configHandler;
    }
}
```
{% endcode %}

## How to use ConfigAPI in your classes

{% code lineNumbers="true" %}
```java
import your.mainclass.project-name

public class YourCommand implements CommandExecutor {

 private final YourProject yourProject = YourProject.getPlugin(YourProject.class);
 
 @Override
 public boolean onCommand(CommandSender sender, Command command, String label, String[] args) {
      Player player = (Player) sender;  
      
      if(args.length == 0) {
           player.sendMessage(yourProject.getConfiguration().get().getConfig().getString("config.prefix"));
           //do stuff here
      }
      return false;
 }    
```
{% endcode %}
