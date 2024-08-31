# HomeAPI

{% hint style="info" %}
The HomeAPI is available since System v.0.4.9.7-dev
{% endhint %}

{% hint style="info" %}
Please note: The HomeAPI is not yet final. It will be changed frequently till the release of System v0.5-stable
{% endhint %}

```java
public class YourProject extends JavaPlugin {

    private YourProject yourProject;
    private HomeAPI homeAPI;

    @Override
    public void onEnable() {
        this.yourProject = this;
        this.homeAPI= new HomeAPI();
    }

    @Override
    public void onDisable() {

    }

    public YourProject getYourProject() {
        return this.yourProject;
    }

    public SettingsAPI getHomeAPI() {
        return this.homeAPI;
    }
}
```
