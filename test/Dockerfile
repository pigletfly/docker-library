FROM centos

RUN yum install net-tools telnet  bridge-utils bind-utils -y
EXPOSE 80 8000

CMD ["python", "-m", "SimpleHTTPServer", "80"]
