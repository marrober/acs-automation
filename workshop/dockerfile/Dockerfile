FROM fedora

USER root

RUN  mkdir /opt/tomcat

RUN dnf -q -y install java-1.8.0-openjdk java-11-openjdk java-1.8.0-openjdk-devel wget

WORKDIR /tmp

RUN wget -q http://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.46/bin/apache-tomcat-9.0.46.tar.gz

RUN tar -xvf apache-tomcat-9.0.46.tar.gz > /dev/null

RUN mv /tmp/apache-tomcat-9.0.46/* /opt/tomcat/.

WORKDIR /opt/tomcat/webapps
RUN curl -O -L https://github.com/AKSarav/SampleWebApp/raw/master/dist/SampleWebApp.war

EXPOSE 8080

USER 1001

CMD ["/opt/tomcat/bin/catalina.sh", "run"]