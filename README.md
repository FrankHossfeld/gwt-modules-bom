# GWT Modules
This BOM can be used to add the latest GWT moduels versions to your project.

To add the BOM, just add this code snippet to your pom:
```xml
  <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>org.gwtproject.modules</groupId>
                <artifactId>gwt-modules</artifactId>
                <version>1.0-SNAPSHOT</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>
```

## Current Versions

