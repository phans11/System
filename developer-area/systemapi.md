# SystemAPI

## **How to hook into System**

```java
import de.isolveproblems.system.api.SystemAPI;

public class YourProject extends JavaPlugin {

    private YourProject yourProject;
    private SystemAPI systemAPI;

    @Override
    public void onEnable() {
        this.yourProject = this;
        this.systemAPI = new SystemAPI();
    }

    @Override
    public void onDisable() {

    }

    public YourProject getYourProject() {
        return this.yourProject;
    }

    public SystemAPI getSystemAPI() {
        return this.systemAPI;
    }
}
```

