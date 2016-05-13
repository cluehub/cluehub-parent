Cluehub - parent POM
===================
[![Build Status](https://travis-ci.org/cluehub/cluehub-parent.svg?branch=master)](https://travis-ci.org/cluehub/cluehub-parent)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.cluehub/cluehub-parent/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.cluehub/cluehub-parent/)


A generic **[Maven](http://maven.apache.org/)** parent **POM** file that comprise some opinionated configurations and plugins to make it easy to manage the building, testing and releasing cycle with minimal configuration in the children projects.

Brief
-------------
(Cluehub parent) CHP has been created to lighten the burden of writing POM files from scratch for typical everyday's small to medium newly created applications.

CHP itself is a child of sonatype's **oss-parent**:
```
<parent>
	<groupId>org.sonatype.oss</groupId>
	<artifactId>oss-parent</artifactId>
	<version>${EVENTUALLY_LATEST_VERSION}</version>
</parent>
```
CHP is intended to be up to date regarding the versions of its parent, dependencies and plugins. Each release of CHP should include the latest release versions of all its dependencies in its time.

CHP release versioning follows the [semantic versioning guidelines](http://semver.org/)

Usage
-------------
Just set this as a parent POM.
```
<parent>
	<groupId>com.cluehub</groupId>
    <artifactId>cluehub-parent</artifactId>
    <version>${LATEST_RELEASE_VERSION}</version>
</parent>
```

Goals
-------------
To provide means for the following common aspects:

- Unit testing and mocking.
- Test coverage reports generation.
- Unified way for logging.
- Auto service discovery.
- Project level validation and rule enforcement.
- Potential bug and code optimization reporting.
- Enhanced API documentation definition support.
- Out of the box release cycle management.
- Artifact auto-signing on release.
- POM and dependency version management.
- Source code license management.
- UTF-8 source code encoding.
- Enforcing standard code style.


Dependencies
-------------
CHP implicitly declares a set of dependencies which are favored by the author, the dependencies are as follows:

- **[junit](http://junit.org)** - for testing.
- **[jmockit](http://jmockit.org/)** - for unit tests dependency mocking.
- **[slf4j-api](http://www.slf4j.org/)** - as a logging interface, it's up to the user to use whatever implementation (there is a certain **[enforcer plugin](https://maven.apache.org/enforcer/maven-enforcer-plugin/)** constrain that favors **[log4j2](http://logging.apache.org/log4j/2.x/)** but that can be overridden, also **[slf4j-simple](http://www.slf4j.org/api/org/slf4j/impl/SimpleLogger.html)** is included by default for running tests.
- **[auto-service](https://github.com/google/auto/tree/master/service)** by Google - for auto service discovery.


Plugins
-------------
Same as dependencies, here are the favored plugins:

- **[maven-gpg-plugin]()** - to sign artifacts before publishing.
- **[maven-enforcer-plugin]()** - for enforcing some rules like using certain slf4j adapters across the whole application.
- **[pegdown-doclet]()** - to be able to write markdown in code documentation.
- **[maven-release-plugin]()** - for releasing to nexus or maven central with revision tagging.
- **[findbugs-maven-plugin]()** - to locate potential bugs and code inhancements.
- **[jacoco-maven-plugin]()** - for coverage reporting also supported by coveralls service.
- **[coveralls-maven-plugin]()** - for reporting to coveralls service.
- **[maven-checkstyle-plugin]()** - for forcing code styling.
- **[license-maven-plugin]()** - to ensure that all the source files contain the copyright notice.
- **[versions-maven-plugin]()** - to check for dependency updates and be able to set the project version manually if needed.


License
-------------
Available under GNU general public license version 3.
