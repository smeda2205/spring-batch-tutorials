# "Hello World!" with Spring Batch 2.1

## Summary

In this tutorial, we will create a simple [Hello World!][hello-world] program with [Spring Batch][spring-batch] and learn some basics for this amazing framework.

## For the Impatient

If you are in a hurry or just the code-first type, you can jump right to the source on [my github repository][github-repo].

## How to setup a simple Spring Batch program?

The setup of a Spring Batch program mostly consists of 3 parts:

* [project setup](#project-setup)
* Spring Batch infrastructure
* Spring Batch Job

### Project Setup<a id="project-setup"></a>
#### Maven
#### Gradle
#### IDE specific Project Setups

To create a project with your favourite IDE, please follow the links to the appropiate documentation.

* [Eclipse][eclipse-help]
* [Intelli J IDEA project setup][intellij-idea-project-setup]
* [Netbeans project setup][netbeans-project-setup]

#### Which Java Libraries are needed?

Each entry in this library list follows the pattern `<library>:<version>`. List is produced with Maven Plugin and command `dependency:list`.

* Spring Version 3.0.6.RELEASE
	* spring-aop
	* spring-asm
	* spring-beans
	* spring-context
	* spring-core
	* spring-expression
	* spring-jdbc
	* spring-tx
* Spring Batch Version 2.1.8.RELEASE
	* spring-batch-core
	* spring-batch-infrastructure
* other
	* aopalliance:1.0
	* xstream:1.3
	* commons-logging:1.1.1
	* jettison:1.1
	* xpp3_min:1.1.4c
* for test
	* commons-collections:3.2
	* commons-dbcp:1.2.2
	* commons-io:jar:1.4
	* commons-pool:1.3
	* junit:4.10
	* hamcrest-core:1.1
	* spring-test:3.0.6.RELEASE
	* spring-batch-test:2.1.8.RELEASE

For Maven users i provided the complete dependency configuration:

```
	<dependencies>
	    <!-- Spring (core) Framework dependencies -->
	    <dependency>
	        <groupId>org.springframework</groupId>
	        <artifactId>spring-beans</artifactId>
	        <version>${spring.framework.version}</version>
	    </dependency>
	    <dependency>
	        <groupId>org.springframework</groupId>
	        <artifactId>spring-context</artifactId>
	        <version>${spring.framework.version}</version>
	    </dependency>
	    <!-- spring-jdbc specified, because spring-batch has
	         older 2.5.6 version configured, we want 3.0.6 here -->
	    <dependency>
	        <groupId>org.springframework</groupId>
	        <artifactId>spring-jdbc</artifactId>
	        <version>${spring.framework.version}</version>
	    </dependency>
	    <!-- Spring Batch dependencies -->
	    <dependency>
	        <groupId>org.springframework.batch</groupId>
	        <artifactId>spring-batch-core</artifactId>
	        <version>${spring.batch.version}</version>
	    </dependency>
	    <dependency>
	        <groupId>org.springframework.batch</groupId>
	        <artifactId>spring-batch-infrastructure</artifactId>
	        <version>${spring.batch.version}</version>
	    </dependency>
	    <!-- test scoped dependencies -->
	    <dependency>
	        <groupId>org.springframework.batch</groupId>
	        <artifactId>spring-batch-test</artifactId>
	        <version>${spring.batch.version}</version>
	        <scope>test</scope>
	    </dependency>
	    <dependency>
	        <groupId>org.springframework</groupId>
	        <artifactId>spring-test</artifactId>
	        <version>${spring.framework.version}</version>
	        <scope>test</scope>            
	    </dependency>
	    <dependency>
	        <groupId>junit</groupId>
	        <artifactId>junit</artifactId>
	        <version>4.10</version>
	        <scope>test</scope>
	    </dependency>
	</dependencies>
```



## Did you know?

Spring Batch was first [introduced][first-introduction] in 2007. Back then the framework was created by Interface21 - now known as [Springsource][springsource] - and [Accenture][accenture]. It has seen only 2 major versions so far, but the [transition from version 1 to 2][changes-1-to-2] included a massive refactoring of the core concepts. In fact the Tasklet used in this tutorial was first released with version 2.0.

## Meta

* tested with:
    * Java 1.6
    * Maven 3
	* [Spring Batch][spring-batch] 2.1.8.RELEASE
	* [Spring Framework(core)][spring-core] 3.0.6.RELEASE
* used IDE: primarily programmed with [Netbeans][netbeans] 7.0
* license: [Apache 2.0 License][apache-license]

[accenture]: http://www.accenture.com/ "Accenture official home page"
[apache-license]: http://www.apache.org/licenses/LICENSE-2.0.txt "Apache 2.0 License"
[changes-1-to-2]: http://static.springsource.org/spring-batch/trunk/migration/2.0-highlights.html "Changes from Spring Batch 1.x to 2.0"
[eclipse-help]: http://www.eclipse.org/documentation/ "Eclipse: Starting Point for Documentation"
[github-repo]: https://github.com/langmi/spring-batch-tutorials "My Github Repository for Spring Batch Tutorials Sources"
[hello-world]: http://en.wikipedia.org/wiki/Hello_world_program "Wikipedia: Hello World Programm"
[intellij-idea-project-setup]: http://www.jetbrains.com/idea/webhelp/creating-new-project-from-scratch.html "Intelli J IDEA: Creating New Project From Scratch"
[first-introduction]: http://forum.springsource.org/showthread.php?38417-Spring-Batch-Announcement "first Spring Batch announcement from 2007"
[netbeans]: http://netbeans.org/ "Netbeans official home page"
[netbeans-project-setup]: http://netbeans.org/kb/docs/java/project-setup.html "Netbeans: Creating, Importing, and Configuring Java Projects"
[springsource]: http://www.springsource.com/ "Springsource official home page"
[spring-batch]: http://static.springsource.org/spring-batch/  "Spring Batch official home page"
[spring-core]: http://www.springsource.org/spring-core/ "Spring Core Framework official home page"