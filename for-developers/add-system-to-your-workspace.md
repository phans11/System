# Using System as Developer

### Using Maven

To be able to use System in your project (if you're running Maven), you can use following settings:

```xml
        <repositories>
		<repository>
		    <id>jitpack.io</id>
		    <url>https://jitpack.io</url>
		</repository>
	</repository>
```

```xml
	<dependency>
	    <groupId>com.github.phans11</groupId>
	    <artifactId>System_Code</artifactId>
	    <version>$version</version>
	</dependency>
```

### Using Gradle

If you do use Gradle to build your project, these settings will suite you:

```gradle
	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```

```gradle
	dependencies {
	        implementation 'com.github.phans11:System_Code:$version'
	}
```

### Making sure your plugin loads before System

To make sure that System recognizes your requirements, your plugin should load before System does. You can do this by adding a `depend` or `soft depend`  option in your plugin.yml, see [this page](https://www.spigotmc.org/wiki/plugin-yml/).  You can use `soft depend` whenever System is not necessary to run your plugin. If you need System to always be there when you run your plugin, you should use `depend`.&#x20;

### Hooking into System

```java
public System getSystem() {
	Plugin plugin = getServer().getPluginManager().getPlugin("System");
		
	// Plugin is not loaded or enabled
	if (plugin == null || !(plugin instanceof System)) {
		return null; // You could also throw an exception if you want to.
	}
		
	return (System) plugin;
}
```
