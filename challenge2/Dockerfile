FROM centos:7

RUN yum -y install httpd

ADD "webserver.tar.gz" "/var/www/html"

ENTRYPOINT [ "/usr/sbin/httpd", "-D", "FOREGROUND" ]

EXPOSE 80