FROM tomcat
COPY target/so-networklayer.war /usr/local/tomcat/webapps.dist/so-networklayer.war
COPY target/server.xml /usr/local/tomcat/conf/server.xml
COPY target/catalina.sh /usr/local/tomcat/bin/catalina.sh
COPY target/extlib/* /usr/local/tomcat/extlib/
COPY target/lib/* /usr/local/tomcat/lib/
COPY target/keystore /usr/local/tomcat/keystore
COPY target/WebToolLicense /usr/nsue/config_local/WebToolLicense