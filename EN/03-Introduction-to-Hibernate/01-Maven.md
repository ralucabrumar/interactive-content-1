# Maven

[slide hideTitle]

# Maven Overview

Maven is a project management framework. 

It manages the build and dependencies of our project, using **XML** files.

The concept of Maven revolves around the build lifecycle.

This means that the process around building a particular project is clearly defined.

The process of building a project contains multiple steps:

- **Compiling** the source code
- Running **unit** and/or **integration** tests
- **Packaging** the compiled code into Jar files
- **Bundling** Jar files into web archive (War) files
- **Deploying** the project to a server

To build a Maven project, we only need to learn a small list of commands.

The **POM** ensures we achieve the desired results.

The Project Object Model, stored in the **pom.xml** file, holds the configuration of our project.

[/slide]

[slide hideTitle]

# Setup - Creating a Maven Project 

Now, let us create a new project by using Maven.

- Select "**Maven**" from the new project panel:

[image assetsSrc="Hibernate.jpg" /]

- Choose the **name** of the project, the current Project **group**, and the project **version**:

[image assetsSrc="Hibernate(2).jpg" /]

- Set up the **name** and **location**:

[image assetsSrc="Hibernate(3).png" /]

- Enable Maven **auto-import**:

[image assetsSrc="Hibernate(4).png" /]

[/slide]

[slide hideTitle]

# Maven Configurations

A Project Object Model (**POM**) is the fundamental unit of work in Maven.

The `pom.xml` file contains all configurations.

When executing a task or goal, Maven looks for this file in the current directory.

Let us take a look at the POM file and its dependencies.

## POM Model

```java
<build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <configuration>
                    <source>15</source>
                    <target>15</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
```

The snippet above is a simplified version of a typical `pom.xml` file.

The `<build>` element contains the build configuration of our project.

In this case, it contains the `<plugins>` element - a list of plugins.

Each `<plugin>` element contains two identifiers.

The `<groupId>` identifier denotes the group a plugin belongs to.

By default, all core Maven artifacts live under the **groupId** `org.apache.maven`.

The `<artifactId>` is the name of our project, but in the case of a plugin, it is `maven-compiler-plugin`.

Every plugin has a specific `<configuration>` property, used to pass values to an underlying system, such as a plugin.

## Dependencies

Most projects are dependent on other projects to build and execute properly.

We declare dependencies using the `<dependency>` tag:

```java
<dependencies>
        <dependency>
            <groupId>org.hibernate</groupId>
            <artifactId>hibernate-core</artifactId>
            <version>5.4.22.Final</version>
        </dependency>
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>8.0.21</version>
        </dependency>
 </dependencies>
```

Each dependency contains **three** elements:

- `groupId` and `artifactId` - the dependency's **coordinates**
- `version` - a dependency version requirement specification, used to **compute the dependency's effective version**

This computation is performed in order to select a version that matches all dependency declaration, preventing **version mismatch** errors.

[/slide]