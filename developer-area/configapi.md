# ConfigAPI

## How to hook into ConfigAPI

```java
import de.isolveproblems.system.api.ConfigAPI;

public class ConfigurationMessages {

    private final YourProject yourProject = YourProject.getPlugin(YourProject.class);

    public ConfigAPI config;

    public void getMessages() {
        config = new ConfigAPI("plugins/YourProject", "config.yml", yourProject);
        
        config.getConfig().addDefault("config.prefix", "&c[YourProject]");
        
        config.saveConfig();
    }
}
```

