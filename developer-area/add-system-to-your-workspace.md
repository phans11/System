# Add System to your Workspace

### Using Maven

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
