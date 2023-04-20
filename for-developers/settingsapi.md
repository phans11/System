# SettingsAPI

## How to hook into SettingsAPI

{% code lineNumbers="true" %}
```java
import de.isolveproblems.system.api.SettingsAPI;

public class YourProject extends JavaPlugin {

    private YourProject yourProject;
    private SettingsAPI settingsAPI;

    @Override
    public void onEnable() {
        this.yourProject = this;
        this.settingsAPI= new SettingsAPI();
    }

    @Override
    public void onDisable() {

    }

    public YourProject getYourProject() {
        return this.yourProject;
    }

    public SettingsAPI getSettingsAPI() {
        return this.settingsAPI;
    }
}
```
{% endcode %}
