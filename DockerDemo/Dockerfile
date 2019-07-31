# Basic setup
FROM centos:7
LABEL maintainer="henry@tld.com"

# Update repos and install httpd
RUN yum -y update && \
    yum -y install httpd && \
    yum clean all

# Expose a port from the container to Docker and run the startup script on launch
EXPOSE 80
CMD ["/usr/sbin/apachectl", "-DFOREGROUND"]