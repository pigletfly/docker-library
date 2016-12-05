FROM debian:jessie

MAINTAINER NGINX Docker Maintainers "docker-maint@nginx.com"

ENV NGINX_VERSION 1.11.6-1~jessie
RUN echo "deb http://mirrors.163.com/debian/ jessie main non-free contrib \n\
deb http://mirrors.163.com/debian/ jessie-updates main non-free contrib \n\
deb http://mirrors.163.com/debian/ jessie-backports main non-free contrib \n\
deb-src http://mirrors.163.com/debian/ jessie main non-free contrib \n\
deb-src http://mirrors.163.com/debian/ jessie-updates main non-free contrib \n\
deb-src http://mirrors.163.com/debian/ jessie-backports main non-free contrib \n\
deb http://mirrors.163.com/debian-security/ jessie/updates main non-free contrib \n\
deb-src http://mirrors.163.com/debian-security/ jessie/updates main non-free contrib \n\
" > /etc/apt/sources.list
RUN apt-get update 
RUN apt-get upgrade -y
RUN apt-get install vim telnet dnsutils -y
RUN apt-key adv --keyserver hkp://pgp.mit.edu:80 --recv-keys 573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62 \
	&& echo "deb http://nginx.org/packages/mainline/debian/ jessie nginx" >> /etc/apt/sources.list \
	&& apt-get update \
	&& apt-get install --no-install-recommends --no-install-suggests -y \
						ca-certificates \
						nginx=${NGINX_VERSION} \
						nginx-module-xslt \
						nginx-module-geoip \
						nginx-module-image-filter \
						nginx-module-perl \
						nginx-module-njs \
						gettext-base \
	&& rm -rf /var/lib/apt/lists/*

# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
	&& ln -sf /dev/stderr /var/log/nginx/error.log

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
