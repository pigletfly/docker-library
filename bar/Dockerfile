FROM centos

RUN curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py"
RUN python get-pip.py
RUN pip install Flask
RUN curl https://gist.githubusercontent.com/pigletfly/77b3decf61fe11c3f4eb6ee307822614/raw/d8e434ea6ef6aaf173dbbcbffe84e3d8ee29bc4e/bar -o run.py
RUN yum install net-tools telnet  bridge-utils bind-utils -y
EXPOSE 8000

CMD ["python", "run.py"]
