FROM centos:7
MAINTAINER SHU

RUN yum -y --setopt=tsflags=nodocs update && \    
yum -y --setopt=tsflags=nodocs install httpd && \   
yum -y install php php-mysql &&\
 yum clean all

EXPOSE 80

# Simple startup script to avoid some issues observed with container restart
ADD run-httpd.sh /run-httpd.sh
ADD gamep.php /gamep.php
ADD index.html /index.html
ADD login.php /login.php
ADD welcome.php /welcome.php
ADD gamep.jpg /gamep.jpg

RUN chmod -v +x /run-httpd.sh

CMD ["/run-httpd.sh"]
