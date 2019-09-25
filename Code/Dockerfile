FROM ubuntu AS build
MAINTAINER raghav.jha@pratian.com
RUN apt-get update
RUN apt-get install -y openjdk-8-jdk
RUN apt-get install -y maven
WORKDIR /code
COPY pom.xml /code
COPY src/. /code/src
RUN mvn package
FROM andreptb/tomcat:7-jdk7
WORKDIR /usr/local/tomcat/webapps/
COPY --from=build /code/target/happytrip-1.0.0-BUILD-SNAPSHOT.war ./happytrip.war



