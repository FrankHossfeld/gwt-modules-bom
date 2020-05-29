# Contributing

If you are interested in making the GWT modules better, fixing a bug, improve a module or building a GWT module from source, then this document is for you.

1.  [Introduction](#introduction)
    1.  [Licensing](#licensing)
2.  [The GWT Community](#community)
    1.  [Please Be Friendly](#befriendly)
    2.  [Where to Discuss GWT](#wheretodiscussgwt)
    3.  [How to Report a Bug](#issuetracking)
3.  [Working with the Code](#workingoncode)
    1.  [Checking out the Source](#checkingout)
    2.  [Compiling from Source](#compiling)
    3.  [Testing](#testing)
4.  [Contributing Code](#contributingcode)
    1.  [Code Style](#codestyle)
    2.  [Submitting Patches](#submittingpatches)
    3.  [GWT Committers](#committers)
5.  [Contributing to Webpage &amp; Documentation](#webpage)

## Introduction<a id="introduction"></a>

As it gets more and more clearer that with the new transpiler J2CL many things we have used in GWT gets removed, we needed a migration path.  We cloned every module from GWT and create a new repo.
We updated the module:
* removed deprecated code
* replace JSNI with JsInterop
* replace generators with annotationp processors
* make sure, that the new modules will compile with J2CL
and tried to keep thing as close as the were in GWT  to make it easy to migrate.

Our goal is to have modules, that work with GWT and J2CL.

### Licensing<a id="licensing"></a>

All GWT modules source and pre-built binaries are provided under the [Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0).

## The GWT Community<a id="community"></a>

The GWT community exists primarily through the [Gitter room](https://gitter.im/gwtproject/gwt), mailing lists, the issue tracker and, to a lesser extent, the source control repository. You are definitely encouraged to contribute to the discussion and you can also help us to keep the effectiveness of the groups high by following and promoting the guidelines listed here.

### Please Be Friendly<a id="befriendly"></a>

Showing courtesy and respect to others is a vital part of the Google culture, and we strongly encourage everyone participating in GWT development to join us in accepting nothing less. Of course, being courteous is not the same as failing to constructively disagree with each other, but it does mean that we should be respectful of each other when enumerating the 42 technical reasons that a particular proposal may not be the best choice. There's never a reason to be antagonistic or dismissive toward anyone who is sincerely trying to contribute to a discussion.

Sure, web development is serious business and all that, but it's also a lot of fun. Let's keep it that way. Let's strive to be one of the friendliest communities in all of open source.

### Where to Discuss GWT<a id="wheretodiscussgwt"></a>

As always, discuss _using_ GWT module in the [official GWT Module Gitter room](https://gitter.im/gwtproject/gwt-modules).

### How to Report a Bug<a id="issuetracking"></a>

Open an issue.

### Compiling from Source<a id="compiling"></a>

To compile from source:

1.  Install [Maven](https://maven.apache.org/download.cgi). We'll assume that the `mvn` command is in your path.
2.  Clone the repo
3.  run `mvn clen install`

### Testing<a id="testing"></a>

Testing is very important to maintaining the quality of GWT. [Unit Tests](#unittesting) should be written for any new code, and changes should be verified to not break existing tests before they are submitted for review.  Keep in mind, that you need to write tests for GWT and J2CL!

## Contributing Code<a id="contributingcode"></a>

All GWT modules are open source. It is quite easy to fix bugs and create new features. Before you fire up your favorite IDE and begin hammering away at that new feature, though, please take the time to read this section and understand the process. While it seems rigorous, we want to keep a high standard of quality in the code base.

### Code Style<a id="codestyle"></a>

To keep the source consistent, readable, diffable and easy to merge, we use a fairly rigid coding style, and all patches will be expected to conform to the style outlined here. To keep things as simple as possible, many of these style rules will be automatically verified by the GWT build; style issues that can't be caught by the build system should be addressed during code review.

To make it easier to format your GWT code correctly, use the [GWT style formatter](https://github.com/google/styleguide)
* for Eclipse (Preferences | Java > Code Style > Formatter | Import...).
* for IntelliJ (Preferences | Code Style > Java | Import ...)
* 
In general, the GWT style is based on [the standard Java conventions](http://java.sun.com/docs/codeconv/html/CodeConvTOC.doc.html), except for the differences spelled out below.

For the record, we know that coding style is often a controversial topic. We acknowledge that plenty of great approaches exist out there. We're simply trying to pick one that is at least somewhat consistent with Oracle's Java coding conventions, codify it well, and stick to it.

#### Comments and Javadoc

Every file should have an Apache license header at the top, prefaced with a copyright notice. A package statement and import statements should follow, each block separated by a blank line. Next is the class or interface declaration. In the Javadoc comments, describe what the class or interface does.

```
/**
 * A simplified, browser-safe timer class. This class serves the same purpose as java.util.Timer,
 * but is simplified because of the single-threaded environment.
 *
 * <p>To schedule a timer, simply create a subclass of it (overriding {@link #run}) and call {@link
 * #schedule} or {@link #scheduleRepeating}.
 *
 * <p>NOTE: If you are using a timer to schedule a UI animation, use
 * <b>org.gwtproject.animation.client.AnimationScheduler</b> or
 * <b>DomGlobal#requestAnimationFrame</b>
 * instead. The browser can optimize your animation for maximum performance.
 */

package org.gwtproject.foo;

import org.gwtproject.bar.Blah;
import org.gwtproject.bar.Yada;

import java.sql.ResultSet;
import java.sql.SQLException;

/**
 * Does X and Y and provides an abstraction for Z.
 */
public class Foo {
  ...
}
```

#### Class Structure and Member Sort Order

Java types should have the following member order:

1.  Nested Types (mixing inner and static classes is okay)
2.  Static Fields
3.  Static Initializers
4.  Static Methods
5.  Instance Fields
6.  Instance Initializers
7.  Constructors
8.  Instance Methods

Members that fall into the same category (e.g. static methods)
should also be sorted in this order based on visibility:

1.  public
2.  protected
3.  default
4.  private

All methods should be sorted alphabetically. Sorting is optional
but recommended for fields. For example, the following class excerpt is
correctly sorted:

```
public abstract class Foo {
  // Type declarations.
  public class FooBaz {
  }
 
  private class FooBar {
  }

  // Static field declarations.
  // Remember, fields do NOT need to be sorted.
  static String B;
  static String A;

  // Static initializer declarations.
  static {
  }

  // Static methods declarations.
  // Remember, methods do need to be sorted.
  static void aStatic() {
  }

  static void bStatic() {
  }

  // Instance field declaration.
  String bField;
  String aField;

  // Instance Initializer declarations.
  {
  }

  // Constructors declaration.
  public Foo() {
  }

  protected Foo(String s) {
  }

  Foo(int i) {
  }

  private Foo(boolean b) {
  }

  // Instance method declaration.
  public void b() {
  }

  public void c() {
  }

  protected void a() {
  }

  protected void d() {
  }

  protected void e() {
  }

  protected void f() {
  }

  String h() {
  }

  // The "abstract" keyword does not modify the position of the method.
  abstract String i();

  void j() {
  }

  private void g() {
  }
}
```

#### Indentation

We use 2-space indents for blocks. No tabs at all, anywhere.

We use 4-space indents after line wraps, including function calls and assignments. For example, this is correct (4 spaces after the newline):

```
Instrument i =
    new Instrument();
```

and this is not correct (2 spaces after the newline):

```
Instrument i =
  new Instrument();
```

#### Imports

The ordering of import statements is:

*   GWT imports
*   Imports from third parties (com, junit, net, org)
*   java and javax

To exactly match the IDE settings, the imports should be:

*   Alphabetical within each grouping. Capital letters are considered to come before lower case letter (e.g. Z before a).
*   There should be a blank line between each major grouping (google, com, junit, net, org, java, javax).

#### Line Length and Wrapping

Each line of text in your code should be at most 100 characters long. Use linefeed characters to break lines (Unix-style). There are some exceptions:

*   Exception: If a comment line contains an example command or a literal URL longer than 100 characters, that line may be longer than 100 characters for ease of cut and paste.
*   Exception: Import lines can go over the limit because humans rarely see them. This also simplifies tool writing.

#### Acronyms in names

Treat acronyms and abbreviations as words. The names are much more readable:

|Good            |Bad             |
|----------------|----------------|
|`XmlHttpRequest`|`XMLHTTPRequest`|
|`getCustomerId` |`getCustomerID` |

This style rule also applies when an acronym or abbreviation is the entire name:

|Good         |Bad          |
|-------------|-------------|
|`class Html` |`class HTML` |
|`String url;`|`String URL;`|
|`long id;`   |`long ID;`   |

Note that this is a reversal of an earlier, regretted decision, and much code in GWT violates this rule. While it's not worth breaking existing APIs for stylistic concerns, all new code should treat acronyms as words.

For further justifications of this style rule, see Effective Java Item 56 (Item 38 in 1st edition) and Java Puzzlers Number 68.

#### Parameterized type names

Parameterized type names should be one capital letter. However, if readability demands longer names (particularly due to having multiple parameters), the name should be capitalized and have suffix "T". In a nutshell, prefer `<T>` or `<K, V>`, and devolve to `<KeyT, ValueT>` if necessary.

| Good           | Bad                                         | Tolerable                          |
|:---------------|:--------------------------------------------|:-----------------------------------|
| `Foo<T>`       | `Foo<FooClientType>`                        |                                    |
| `Bar<K, V>`    | `Bar<KeyType, ValueType>`                   |                                    |
| `Baz<V, E, X>` | `Baz<EventType, ErrorType, ExpressionType>` | `Baz<EventT, ErrorT, ExpressionT>` |

## Submitting Patches<a id="submittingpatches"></a>

Please do submit code. Here's what you need to do:

1.  Decide which code you want to submit. A submission should be a set of changes that addresses one issue in the GWT Module issue tracker. Please don't mix more than one logical change per PR, because it makes the history hard to follow. If you want to make a change that doesn't have a corresponding issue in the issue tracker, please create one.
2.  Also, coordinate with team members that are listed on the issue in question. This ensures that work isn't being duplicated and communicating your plan early also generally leads to better patches.
3.  Ensure that your code adheres to the [GWT source code style](#codestyle).
4.  Ensure that there are unit tests for your code.
5.  To merge the PR you need a member of the GWT Engineering team which merges the PR.

### GWT Module Committers<a id="committers"></a>

The current members of the GWT Engineering Team are the only committers at present. In the great tradition of eating one's own dogfood, we will be requiring each new GWT engineering team member to earn the right to become a committer by following the procedures in this document, writing consistently great code, and demonstrating repeatedly that he or she truly gets the zen of GWT.

### Global .gitignore<a id="global_gitignore"></a>

Since our .gitignore files don't contain IDE or OS specific .gitignore entries you should setup your global .gitignore.

[This](https://help.github.com/articles/ignoring-files) is how you setup a global .gitignore.

[Here](https://github.com/github/gitignore/tree/master/Global) you find a list of IDE specific global .gitignore files.

