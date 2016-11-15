FROM tomcat:9-alpine
COPY app-core.war /usr/local/tomcat/webapps
COPY app.war /usr/local/tomcat/webapps

CMD ["catalina.sh", "run"]
