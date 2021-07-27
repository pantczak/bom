# Bill of Materials for my Projects

This repository contains Bill of Materials (BOM) POM for my projects.

Main goal for creating this repository was to streamline dependency management. (as it is a well known common annoyance)
That's why Travis CI along with GitHub Dependabot were used. (apart from whole no versions in pom.xml needed)

## Status

[![CircleCI](https://circleci.com/gh/pantczak/bom.svg?style=svg)](https://circleci.com/gh/pantczak/bom)

## Usage

There are two main ways to use this BOM file

* Inherit from parent

```xml
<project>  <!--skipped lines-->
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.pantczak</groupId>
    <artifactId>pantczak-project</artifactId>
    <version>1.2.1</version>
    <packaging>pom</packaging>
    
    <parent>
        <groupId>com.pantczak</groupId>
        <artifactId>bom</artifactId>
        <version>0.0.1</version>
    </parent>
    
</project>
```

* Import the BOM

```xml

<project>  <!--skipped lines-->
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.pantczak</groupId>
    <artifactId>pantczak-project</artifactId>
    <version>1.2.1</version>
    <packaging>pom</packaging>
    
    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>com.pantczak</groupId>
                <artifactId>bom</artifactId>
                <version>0.0.1</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>
    
</project>

```
