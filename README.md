# GWT Modules
This BOM (Bill Of Materials) can be used to add the latest versions of GWT modules to your project. The versions included in this BOM have been tested together.

To use the BOM inside your pom, add the following code snippet:
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
Next, add a dependency definition for each dependency you would like to use inside your pom.

This example shows, how to add **gwt-timer** to your pom:
```xml
  <dependency>
    <groupId>org.gwtproject.timer</groupid>
    <artifactId>gwt-timer</artifactId>
  </dependency>
```
Keep in mind, you do not need to add a **version**-tag.

## Current Versions

This is a list of the containing modules and their versions:

| Module                    |   Version    | Repo                                                                                                               |
|:--------------------------|:------------:|:-------------------------------------------------------------------------------------------------------------------|
| gwt-callback              | 1.0-SNAPSHOT | [https://github.com/gwtproject/gwt-callback](https://github.com/gwtproject/gwt-callback)                           |
| gwt-core                  | 1.0-SNAPSHOT | [https://github.com/gwtproject/gwt-core](https://github.com/gwtproject/gwt-core)                                   |
| gwt-dom-style-definitions | 1.0-SNAPSHOT | [https://github.com/gwtproject/gwt-dom-style-definitions](https://github.com/gwtproject/gwt-dom-style-definitions) |
| gwt-geolocation           | 1.0-SNAPSHOT | [https://github.com/gwtproject/gwt-geolocation](https://github.com/gwtproject/gwt-geolocation)                     |
| gwt-regexp                | 1.0-SNAPSHOT | [https://github.com/gwtproject/gwt-regexp](https://github.com/gwtproject/gwt-regexp)                               |
| gwt-timer                 | 1.0-SNAPSHOT | [https://github.com/gwtproject/gwt-timer](https://github.com/gwtproject/gwt-timer)                                 |


