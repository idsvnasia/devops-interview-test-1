# Timo DevOps Engineer Interview Test 1

## Context
The source code for `demo` java web application can be found in `demo` directory. Your task as DevOps Engineer is to setup an automated software delivery for `demo` application.

### How to build
In `demo` directory, run the following command to build the web application:

    ./gradlew build

OpenJDK 1.8 or later is required to build this application.

### How to run
If the build completed successfully, an executable jar file will be created in `build/libs` directory, e.g `build/libs/demo-0.0.1-SNAPSHOT.jar`. Run the application with:

    java -jar build/libs/demo-0.0.1-SNAPSHOT.jar

### How to test
Now that the service is up, visit http://localhost:8080/greeting, where you should see:

    {"id":1,"content":"Hello, World!"}

Provide a `name` query string parameter by visiting http://localhost:8080/greeting?name=User. Notice how the value of the `content` attribute changes from `Hello, World!` to `Hello, User!`, as the following listing shows:

    {"id":2,"content":"Hello, User!"}

### How to change version
Edit the file build.gradle, change the line start with `version = ....` with your desired version.

## Tasks
You will need to use public git repo hosting service such as github or gitlab.com, and a public CI/CD service of your choice.

Clone this repo to your own account and send the interviewer:
- the link to your repo
- the output of the CI/CD tool

Complete the following tasks:

1. Build the `demo` application automatically whenever there is a new commit to `master` branch. The artifact is the executable jar file.
2. Package this application in docker image, using `centos:7` as base image. The name of the docker image should be `demo:<version>`, where version is the version of the application.
3. Change the artifact of task 1 from executable jar file to docker image in step 2.
4. Whenever there is a new tag that match `vX.X.X` where X is an integer, e.g v1.5.17, trigger the build automatically and change the version of the application to match the tag.
