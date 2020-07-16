# GWT Module Migration
To prepare GWT for J2CL the GWT modules need to separated from GWT.
There fore we need to create separate artifacts for each module. These artifacts will be located in separate repos.

## Module Requirements
We made several decisions how to set up and implement the modules:

1. every module will have it's own repository
2. use Maven as build tool
3. structure the Maven project like this:
    * parent module
        * one Maven child module for the module itself (name: **gwt-[module name]**)
        * one Maven child module for GWT2-tests (name: ****)
        * one Maven child module for GWT2-tests (name: **gwt-[module name]-gwt2-tests**)
        * one Maven child module for j2cl-tests (name: **gwt-[module name]-j2cl-tests**)
        * one Maven child module for junit-tests (name: **gwt-[module name]-junit-tests**), if needed
        * one Maven child module running a server ir integration tests (name: **gwt-[module name]-test-service**), if needed
4. locate the source code inside the jar
5. use the [fmt-maven-plugin](https://github.com/coveooss/fmt-maven-plugin) to format the code
6. use the [license-maven-plugin](https://github.com/mycila/license-maven-plugin) to set up the license header
7. add a `README.md`-file that describes the purpose of the module
8. add a `LICENSE`-file containing the Apache 2 license
9. add a GitHub action workflow that build the repo for Java 8 and call it `CI`
11. add a `.gitignore`-file
12. add additional docs

**Important Note**

Even we are using a Maven multi module structure, the Maven child modules do not refer the parent pom!

## System requirements
All modules requires at least GWT 2.9.0 and Elemental2 1.0.0-


## Example
[gwt-timer](https://github.com/FrankHossfeld/gwt-timer) is already migrated and uses the example structure. You can copy the files and structure from this Repo and use it as a base to start.

## GitFlow
We will have a master branch. In case you want to fix a bug or add a feature, fork the repo, do your changes and create a PR. A member of the GWT engineering team will work on your PR.

The Snap-Shots version will always be `HEAD_SBAPSHOT`.

Doing a realease requires a branch called `release/x.x.x`.

## Formatting
We will use the [fmt-maven-plugin](https://github.com/coveooss/fmt-maven-plugin) to format the code.

The plugin uses the [google-java-format](https://github.com/google/google-java-format) which follows [Google's code styleguide](https://google.github.io/styleguide/javaguide.html).

If you want your IDE to stick to the same format, check out the [available configuration files](https://github.com/google/styleguide).

* [Eclipse](https://github.com/google/styleguide/blob/gh-pages/eclipse-java-google-style.xml)
* [IntelliJ IDEA](https://github.com/google/styleguide/blob/gh-pages/intellij-java-google-style.xml)

and import this file to your IDE.

## Example implementations

### GIT Ignore File
Use this file as .gitignore in the module project:

```
# NOTE: we don't include IDE-specific files (e.g. IntelliJ's *.iml and .idea/) on-purpose.
# Those patterns should go in a global gitignore or repository-specific excludes.
# See http://www.gwtproject.org/makinggwtbetter.html#global_gitignore

target/
```

### GitHib Action 'CI'
This is the code used for the 'CI' action in GitHub:

```yaml
# This workflow will build a Java project with Maven
# For more information see: https://help.github.com/actions/language-and-framework-guides/building-and-testing-java-with-maven

name: CI

on: [push, pull_request]

jobs:
  build:

    runs-on: ubuntu-latest
    strategy:
      matrix:
        java_version: [ 8 ]

    steps:
      - uses: actions/checkout@v2
      - name: Set up ${{ matrix.java_version }}
        uses: actions/setup-java@v1
        with:
          java-version: ${{ matrix.java_version }}

      - name: Build with Maven
        run: mvn -B verify -V -B -ntp -e
```
and call that file `build.yaml`

This action ensures, that the pull will work without any errors.