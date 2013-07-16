# Dropwizard + Gradle = &hearts; [![Build Status](https://secure.travis-ci.org/smarchive/dropwizard-gradle.png)](http://travis-ci.org/smarchive/dropwizard-gradle)

Minimal example of getting Dropwizard going with Gradle (instead of Maven).

## Gotchas

You need Gradle 1.1 or higher, otherwise you'll run into a [dependency resolution bug](http://issues.gradle.org/browse/GRADLE-2285).

## Jar

This example is using only the standard [Gradle jar task](http://www.gradle.org/docs/current/userguide/java_plugin.html) from the Java plugin. This
will create a JAR file of the project including all dependencies, similar to the [Maven Assembly Plugin](http://maven.apache.org/plugins/maven-assembly-plugin/)
or the [Maven Shade Plugin](http://maven.apache.org/plugins/maven-shade-plugin/).

To create a JAR with all dependencies just run `./gradlew jar`. The resulting JAR will be saved as `./build/libs/dropwizard-gradle-standalone.jar`.

You can simply run the application with `java -jar build/libs/dropwizard-gradle-standalone.jar server src/dist/config/helloworld.yml`.

## Gradle Application Plugin

An alternative to creating a fat JAR is using the [Gradle Application Plugin](http://www.gradle.org/docs/current/userguide/application_plugin.html).

To create a distributable ZIP archive including all dependencies for your application just run `gradle distZip`. The
resulting archive will be saved as `./build/distributions/dropwizard-gradle.zip`.

You can also use the `run` task to start the application.
