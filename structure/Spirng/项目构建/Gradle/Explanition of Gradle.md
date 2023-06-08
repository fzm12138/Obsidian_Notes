###### Common projects conductor
- Ant
	- Advantages: Fast and flexible
	- Disadvantages: complex
- Maven
	- Advantages: Promise priority、coordinate dependencies control、concern package manage
	- Disadvantages:Not flexible and slower than gradle
- Gradle
	- Advantages: Flexible and promise priority、support remote repository and concern package manage 
	- Disadvantages: hard and bad version compatible 
### JDK
- JDK version must be 1.8 or over 1.8

### Default Directory structure is the same as Maven
#### Notice:
- Only war project has webapp directory and jar has not
- gradlew and gradew.bat excute specify wrapper-version's gradle commend not local gradle commend
### Common commends 
- ***gradle clean:*** clean build directory
- ***gradle classes:*** complile codes and config files
- ***gradle test:*** compile test-codes and generate report
- ***grade build:*** build the project
- ***gradle build -x test:*** Jump off test phase and build
###### Caution: gradle commend needs to excute in directory which has`build.gradle`

### Wrapper
`GradleWrapper` is actually a package of `gradle` to solve the problem that different projects needs different versions of gradle
