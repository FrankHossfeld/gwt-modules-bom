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

| Module                    | Version (Snapshot) | Version (Release) | Repo                                                                                                               |
|:--------------------------|:------------------:|:-----------------:|:-------------------------------------------------------------------------------------------------------------------|
| gwt-aria                  |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-aria](https://github.com/gwtproject/gwt-aria)                                   |
| gwt-callback              |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-callback](https://github.com/gwtproject/gwt-callback)                           |
| gwt-core                  |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-core](https://github.com/gwtproject/gwt-core)                                   |
| gwt-dom-style-definitions |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-dom-style-definitions](https://github.com/gwtproject/gwt-dom-style-definitions) |
| gwt-dom                   |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-dom](https://github.com/gwtproject/gwt-dom)                                     |
| gwt-editor                |   HEAD-SNAPSHOT    |      1.0-RC1      | [https://github.com/gwtproject/gwt-editor](https://github.com/gwtproject/gwt-editor)                               |
| gwt-event                 |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-event](https://github.com/gwtproject/gwt-event)                                 |
| gwt-event-dom             |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-event-dom](https://github.com/gwtproject/gwt-event-dom)                         |
| gwt-jsonp                 |         -          |         -         | [https://github.com/gwtproject/gwt-jsonp](https://github.com/gwtproject/gwt-jsonp)                                 |
| gwt-regexp                |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-regexp](https://github.com/gwtproject/gwt-regexp)                               |
| gwt-safecss               |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-safehtml](https://github.com/gwtproject/gwt-safehtml)                           |
| gwt-safehtml              |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-safehtml](https://github.com/gwtproject/gwt-safehtml)                           |
| gwt-timer                 |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-timer](https://github.com/gwtproject/gwt-timer)                                 |
| gwt-typedarrays           |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-typedarrays](https://github.com/gwtproject/gwt-typedarrays)                     |
| gwt-xhr                   |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-xhr](https://github.com/gwtproject/gwt-xhr)                                     |
| gwt-xml                   |   HEAD-SNAPSHOT    |         -         | [https://github.com/gwtproject/gwt-xml](https://github.com/gwtproject/gwt-xml)                                     |

Keep in mind, that 1.0-SNAPSHOT will be the only version, that works with GWT 2.8.2 and Elemental2 1.0.0-RC1. All other versions require GWT 2.9.0 and Elemental2 1.1.0.

## Dependency Matrix

This is a list of modules and the dependencies:

| Module                    | Depends on                                                                             |
|:--------------------------|:---------------------------------------------------------------------------------------|
| gwt-aria                  | gwt-dom                                                                                |
| gwt-core                  | -                                                                                      |
| gwt-callback              | -                                                                                      |
| gwt-dom-style-definitions | -                                                                                      |
| gwt-dom                   | gwt-core, gwt-dom-style-definitions, gwt-event, gwt-regexp, gwt-safecss, gwt-safehtml  |
| gwt-editor                | gwt-event                                                                              |
| gwt-event                 | -                                                                                      |
| gwt-event-dom             | gwt-dom, gwt-event, gwt-event-legacy                                                   |
| gwt-jsonp                 | gwt-callback, gwt-safehtml, gwt-timer                                                  |
| gwt-regexp                | -                                                                                      |
| gwt-safecss               | gwt-dom-style-definitions, gwt-safehtml                                                |
| gwt-safehtml              | gwt-core, gwt-safecss (test)                                                           |
| gwt-timer                 | -                                                                                      |
| gwt-typedarrays           | -                                                                                      |
| gwt-xhr                   | gwt-typedarrays                                                                        |
| gwt-xml                   | -                                                                                      |

need another check:


| Module          | Depends on                              |
|:----------------|:----------------------------------------|
| gwt-aria        | gwt-core, gwt-dom                       |
| gwt-activity    | gwt-place                               |
| gwt-animation   | gwt-timer, gwt-core, gwt-dom            |
| gwt-geolocation | -                                       |
| gwt-http        | -                                       |
| gwt-json        | gwt-core                                |
| gwt-jsonp       | gwt-callback, gwt-timer, gwt-safehtml   |
| gwt-layout      | gwt-aria, gwt-core, gwt-dom             |
| gwt-storage     | gwt-event                               |
