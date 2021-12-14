# Timo DevOps Engineer Interview Test
# Build the artifact:
./gradlew build && java -jar build/libs/demo:1.1.2.jar
#
# Containerize the application:
docker build --build-arg JAR_FILE=build/libs/demo-1.1.2-SNAPSHOT.jar  -t idsvnasia/demo-spring-boot:1.1.2  .
#
#
kuber@kafka:~/devops-interview-test-1/demo$ docker images
REPOSITORY                   TAG            IMAGE ID       CREATED         SIZE
idsvnasia/demo-spring-boot   1.1.2          ff9bfcabe150   5 minutes ago   122MB
hello-world                  latest         feb5d9fea6a5   2 months ago    13.3kB
openjdk                      8-jdk-alpine   a3562aa0b991   2 years ago     105MB
