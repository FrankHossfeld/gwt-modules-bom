# GWT Modules
This BOM (Bill Of Materials) can be used to add the latest versions of GWT modules to your project. The versions included in this BOM have been tested together.

To use the BOM inside your pom, add the following code snippet:
```xml
  <dependencyManagement>
    <dependencies>
      <dependency>
        <groupId>org.gwtproject.modules</groupId>
        <artifactId>gwt-modules</artifactId>
        <version>1.0.0-RC1</version>
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

| Module                    | Version (Snapshot) | Version (Release) | Repo                                                                                                               |
|:--------------------------|:------------------:|:-----------------:|:-------------------------------------------------------------------------------------------------------------------|
| gwt-activity              |         -          |         -         | [https://github.com/gwtproject/gwt-activity](https://github.com/gwtproject/gwt-activity)                           |
| gwt-animation             |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-animation](https://github.com/gwtproject/gwt-animation)                         |
| gwt-aria                  |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-aria](https://github.com/gwtproject/gwt-aria)                                   |
| gwt-callback              |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-callback](https://github.com/gwtproject/gwt-callback)                           |
| gwt-core                  |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-core](https://github.com/gwtproject/gwt-core)                                   |
| gwt-dom                   |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-dom](https://github.com/gwtproject/gwt-dom)                                     |
| gwt-dom-style-definitions |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-dom-style-definitions](https://github.com/gwtproject/gwt-dom-style-definitions) |
| gwt-editor                |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-editor](https://github.com/gwtproject/gwt-editor)                               |
| gwt-event                 |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-event](https://github.com/gwtproject/gwt-event)                                 |
| gwt-event-dom             |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-event-dom](https://github.com/gwtproject/gwt-event-dom)                         |
| gwt-geolocation           |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-geolocation](https://github.com/gwtproject/gwt-geolocation)                     |
| gwt-history               |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-history](https://github.com/gwtproject/gwt-history)                             |
| gwt-http                  |   HEAD-SNAPSHOT    |     1.0.0-RC2     | [https://github.com/gwtproject/gwt-http](https://github.com/gwtproject/gwt-http)                                   |
| gwt-json                  |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-json](https://github.com/gwtproject/gwt-json)                                   |
| gwt-jsonp                 |         -          |         -         | [https://github.com/gwtproject/gwt-jsonp](https://github.com/gwtproject/gwt-jsonp)                                 |
| gwt-layout                |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-layout](https://github.com/gwtproject/gwt-layout)                               |
| gwt-places                |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-places](https://github.com/gwtproject/gwt-places)                               |
| gwt-regexp                |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-regexp](https://github.com/gwtproject/gwt-regexp)                               |
| gwt-safehtml              |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-safehtml](https://github.com/gwtproject/gwt-safehtml)                           |
| gwt-storage               |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-storage](https://github.com/gwtproject/gwt-storagel)                            |
| gwt-timer                 |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-timer](https://github.com/gwtproject/gwt-timer)                                 |
| gwt-typedarrays           |   HEAD-SNAPSHOT    |     1.0.0-RC2     | [https://github.com/gwtproject/gwt-typedarrays](https://github.com/gwtproject/gwt-typedarrays)                     |
| gwt-window                |   HEAD-SNAPSHOT    |     1.0.0-RC2     | [https://github.com/gwtproject/gwt-window](https://github.com/gwtproject/gwt-window)                               |
| gwt-xhr                   |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-xhr](https://github.com/gwtproject/gwt-xhr)                                     |
| gwt-xml                   |   HEAD-SNAPSHOT    |     1.0.0-RC1     | [https://github.com/gwtproject/gwt-xml](https://github.com/gwtproject/gwt-xml)                                     |

Keep in mind, that 1.0-SNAPSHOT will be the only version, that works with GWT 2.8.2 and Elemental2 1.0.0-RC1. All other versions **require GWT 2.9.0 and Elemental2 1.1.0**.

## Dependency Matrix

This is a list of modules and the dependencies:

| Module                    | Depends on                                                               |
|:--------------------------|:-------------------------------------------------------------------------|
| gwt-activity              | gwt-event, gwt-place?, gwt-widget?                                       |
| gwt-animation             | gwt-core, gwt-dom, gwt-timer                                             |
| gwt-aria                  | gwt-dom                                                                  |
| gwt-callback              | -                                                                        |
| gwt-core                  | -                                                                        |
| gwt-callback              | -                                                                        |
| gwt-dom                   | gwt-core, gwt-dom-style-definitions, gwt-event, gwt-regexp, gwt-safehtml |
| gwt-dom-style-definitions | -                                                                        |
| gwt-editor                | gwt-event                                                                |
| gwt-event                 | -                                                                        |
| gwt-event-dom             | gwt-dom, gwt-event, gwt-event-legacy                                     |
| gwt-geolocation           | -                                                                        |
| gwt-history               | gwt-event                                                                |
| gwt-http                  | -                                                                        |
| gwt-json                  | gwt-core                                                                 |
| gwt-jsonp                 | gwt-callback?, gwt-safehtml?, gwt-timer?                                 |
| gwt-layout                | gwt-animationm, gwt-aria, gwt-dom, gwt-dom-style-definitions             |
| gwt-places                | gwt-event                                                                |
| gwt-regexp                | -                                                                        |
| gwt-safehtml              | gwt-core, gwt-dom-style-definitions                                      |
| gwt-storage               | gwt-event, gwt-event                                                     |
| gwt-timer                 | -                                                                        |
| gwt-typedarrays           | gwt-core                                                                 |
| gwt-window                | gwt-event, gwt-http                                                      |
| gwt-xhr                   | gwt-typedarrays                                                          |
| gwt-xml                   | -                                                                        |



