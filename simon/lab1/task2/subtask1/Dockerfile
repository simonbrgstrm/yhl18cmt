FROM maven:3.6.0-jdk-11 AS build

COPY src /tmp/src/
COPY pom.xml /tmp/
WORKDIR /tmp
RUN mvn install

FROM tomcat:9.0.30-jdk11

COPY --from=build /tmp/target/*.war $CATALINA_HOME/webapps/ROOT.war
EXPOSE 8080
