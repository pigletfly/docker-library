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

RUN rm -rf /etc/nginx/conf.d/* /tmp/* /var/tmp/* /var/run/nginx \
&& rm -f /etc/nginx/nginx.conf && mkdir /var/run/nginx && chown nginx /var/run/nginx && chmod 777 /var/run/nginx \
# forward request and error logs to docker log collector
&& ln -sf /dev/stdout /var/log/nginx/docker-access.log \
&& ln -sf /dev/stderr /var/log/nginx/docker-error.log

# nginx site conf
COPY ./nginx.conf /etc/nginx/nginx.conf

EXPOSE 80 443

CMD ["nginx","-g","daemon off;"]
