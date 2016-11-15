FROM tomcat:9-alpine
COPY build/distributions/war/app-core.war /usr/local/tomcat/webapps
COPY build/distributions/war/app.war /usr/local/tomcat/webapps

CMD ["catalina.sh", "run"]
