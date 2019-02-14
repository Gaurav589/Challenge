
**1st task Dockerizing the system**

1st:- check the required software git, JDK8, Maven3

2nd:- download the repo from https://github.com/Damianofds/taskmanager.git

3rd:- As per the mention in the 1st task binaries are broken.
So fix the the Binary first and for that Please open the POM.xml file 

Remove the line from 258 to 274 and save the pom file

https://github.com/Damianofds/taskmanager/blob/master/pom.xml#L258

run the Blow command to Build the Artifacts:-

## Build

### Building with maven

Clone this repo and build first the **web** modules: *endpoints*, *service*, *persistance*.
Note that the latter 2 are shared also with the scheduler.

```
#$ mvn clean install -Pweb

```

Then build the **scheduler**:
```
#$ mvn clean install -Pscheduler

```

After createing the JAR, copy both the JAR under the folder called

https://github.com/Damianofds/taskmanager/tree/master/docker-singleimage 

Gauravs-MacBook-Pro:docker-singleimage gauravagnihotri$ pwd
/Users/gauravagnihotri/all/taskmanager-master/docker-singleimage

Gauravs-MacBook-Pro:docker-singleimage gauravagnihotri$ ls
Dockerfile			endpoints-0.1-SNAPSHOT.jar	scheduler-0.1-SNAPSHOT.jar
Readme.md			launcher.sh

Now run the below command:-

* run `#$ docker build -t taskmanager-all:gaurav .`
* Run the dockerimage created forwarding port 8080 `#$ docker run -p 8080:8080 taskmanager-all:gaurav`

Now check the local host with port 8080

localhost:8080













