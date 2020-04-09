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
Add a dependncy definition for each dependency you would like to use inside your pom.
This example shows, how to add **gwt-timer** to your pom:
```xml
  <dependency>
    <groupId>org.gwtproject.gwt-timer</groupid>
    <artifactId>gwt-timer</artifactId>
  </dependency>
```
Keep in mind, you do not need to add a **version**-tag.

## Current Versions

This is a list of the containing modules and their versions:

| Module                            | Version               |
|-----------------------------------|:---------------------:|
| gwt-callback                      |  1.0-SNAPSHOT         |
| gwt-core                          |  1.0-SNAPSHOT         |
| gwt-dom-style-definitions         |  1.0-SNAPSHOT         |
| gwt-geolocation                   |  1.0-SNAPSHOT         |
| gwt-regexp                        |  1.0-SNAPSHOT         |
| gwt-timer                         |  1.0-SNAPSHOT         |
| gwt-core                          |  1.0-SNAPSHOT         |
