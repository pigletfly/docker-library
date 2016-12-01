FROM centos
RUN yum install telnet nslookup net-tools -y
ENTRYPOINT ['/usr/bin/python','-m','SimpleHTTPServer','80']
