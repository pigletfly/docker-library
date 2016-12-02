# Pull base image.
FROM centos

# Should something be wrong
MAINTAINER Nicholas Anderson, nander13@gmu.edu

# Add nginx official repository
ADD nginx.repo /etc/yum.repos.d/nginx.repo

# Install nginx and apply updates
RUN yum update -y
RUN yum install -y nginx
RUN yum install bind-utils telnet nslookup net-tools -y

# Let Docker handle the daemon
RUN echo "\ndaemon off;" >> /etc/nginx/nginx.conf

# Attach volumes.
VOLUME /etc/nginx/sites-enabled
VOLUME /var/log/nginx

# Set working directory.
WORKDIR /etc/nginx

# Expose ports.
EXPOSE 80
EXPOSE 443

# Define default command.
ENTRYPOINT ["nginx"]
