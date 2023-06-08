### What is it?
- Helping engineers constructing project
- Tell Maven what .jar packages we need and maven will download them automaticly
### Directory restricted by maven
```java
project---src---              |---resources// resources
		|      |------main----|--java      //codes
		|      |
		|      |----test-----java          //unit test code
	   dom               |---resources
	   //maven-config
```
### Basic orders
-  `-v` select version of maven
- `compile` compile ***.java*** to ***.class***
- `test`  excute test
- `package` package project into ***.jar*** 
- `clean` delete **target** directory
- `install` put current project into local maven repository
### What is a mvn repository？
###### It's using for manage all .jar ,divided into two types:
- ***local repository:*** Maven local .jar packages repository
- ***central repository:*** Remote repository supported by official
- When compliling a project ,mvn find .jar from local repository and if nothing compares than downloads from central repository
### What is coordinate
- coordinate is the unique identifier and mvn find .jar accroding to coordinate
eg: groupId and artifactId construted a jar-coordinate
```xml
<dependency>
   <groupId>cn.missbe.web.search</groupId>
   <artifactId>resource-search</artifactId>
   <packaging>jar</packaging>
   <version>1.0-SNAPSHOT</version>
</dependency>
```
- ***groupId***: Project-Name which needs jar
- ***artifactId***: Module-name
- ***version***: version code
- /