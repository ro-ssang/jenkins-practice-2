FROM tomcat:9

RUN mv webapps webapps2 && \
    mv webapps.dist webapps

COPY ./config/context.xml /usr/local/tomcat/webapps/manager/META-INF/context.xml
COPY ./config/context.xml /usr/local/tomcat/webapps/host-manager/META-INF/context.xml
COPY ./config/tomcat-users.xml /usr/local/tomcat/conf/tomcat-users.xml