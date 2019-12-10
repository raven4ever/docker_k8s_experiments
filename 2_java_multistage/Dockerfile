# build the source code of the app
FROM maven:3.6-alpine AS BUILDER

WORKDIR /tmp

COPY app/pom.xml .
COPY app/src/ ./src/

RUN mvn clean install


# deploy the app to tomcat
FROM tomcat:9-alpine

COPY --from=BUILDER /tmp/target/app.war $CATALINA_HOME/webapps/web.war

HEALTHCHECK --interval=1m --timeout=3s CMD wget --quiet --tries=1 --spider http://localhost:8080/web/ || exit 1