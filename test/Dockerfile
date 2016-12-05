FROM centos

RUN yum install net-tools  bridge-utils bind-utils -y
EXPOSE 80 8080

CMD ["python", "-m", "SimpleHTTPServer"]
