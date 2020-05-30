# GWT Modules
This BOM (Bill Of Materials) can be used to add the latest versions of GWT modules to your project. The versions included in this BOM have been tested together.

To use the BOM inside your pom, add the following code snippet:
```xml
  <dependencyManagement>
    <dependencies>
      <dependency>
        <groupId>org.gwtproject.modules</groupId>
        <artifactId>gwt-modules</artifactId>
        <version>1.0.0-20200415-1204</version>
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

This is a list of modules and their versions contained in this BOM:

| Module                    |   Version    | Repo                                                                                                               |
|:--------------------------|:------------:|:-------------------------------------------------------------------------------------------------------------------|
| gwt-callback              |  1.0.0-RC1   | [https://github.com/gwtproject/gwt-callback](https://github.com/gwtproject/gwt-callback)                           |
| gwt-core                  | 1.0-SNAPSHOT | [https://github.com/gwtproject/gwt-core](https://github.com/gwtproject/gwt-core)                                   |
| gwt-dom-style-definitions |  1.0.0-RC1   | [https://github.com/gwtproject/gwt-dom-style-definitions](https://github.com/gwtproject/gwt-dom-style-definitions) |
| gwt-geolocation           | 1.0-SNAPSHOT | [https://github.com/gwtproject/gwt-geolocation](https://github.com/gwtproject/gwt-geolocation)                     |
| gwt-regexp                | 1.0-SNAPSHOT | [https://github.com/gwtproject/gwt-regexp](https://github.com/gwtproject/gwt-regexp)                               |
| gwt-timer                 |  1.0.0-RC1   | [https://github.com/gwtproject/gwt-timer](https://github.com/gwtproject/gwt-timer)                                 |
| gwt-typedarrays           | 1.0-SNAPSHOT | [https://github.com/gwtproject/gwt-typedarrays](https://github.com/gwtproject/gwt-typedarrays)                     |

## Dependency Matrix

This is a list of modules and the dependencies to other moules:

| Module                    | Depends on                              |
|:--------------------------|:----------------------------------------|
| gwt-activity              | gwt-place                               |
| gwt-animation             | gwt-timer, gwt-core, gwt-dom            |
| gwt-aria                  | gwt-core                                |
| gwt-callback              | -                                       |
| gwt-core                  | -                                       |
| gwt-dom-style-definitions | -                                       |
| gwt-editor                | gwt-event                               |
| gwt-event-dom             | gwt-dom, gwt-event                      |
| gwt-geolocation           | -                                       |
| gwt-http                  | -                                       |
| gwt-json                  | gwt-core                                |
| gwt-jsonp                 | gwt-callback, gwt-timer, gwt-safehtml   |
| gwt-layout                | gwt-ara, gwt-core, gwt-dom              |
| gwt-regexp                | -                                       |
| gwt-safecss               | gwt-dom-style-definitions, gwt-safehtml |
| gwt-storage               | gwt-event                               |
| gwt-timer                 | -                                       |
| gwt-typedarrays           | -                                       |
| gwt-xhr                   | gwt-typedarrays                         |
