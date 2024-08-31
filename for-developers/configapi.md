# ConfigAPI

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
