FROM centos:7

RUN yum update -y && \
    yum install tomcat -y && \
    yum clean all && \
    rm -rf /var/cache/yum

RUN mkdir -p /usr/share/tomcat/webapps/ROOT
COPY files/index.html /usr/share/tomcat/webapps/ROOT/index.html

EXPOSE 8080
CMD /usr/libexec/tomcat/server start
