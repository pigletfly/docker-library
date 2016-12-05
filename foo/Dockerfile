FROM centos

RUN curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py"
RUN python get-pip.py
RUN pip install Flask
RUN curl https://gist.githubusercontent.com/pigletfly/853b2431e2f2c6ba584f782dec1befaf/raw/988b29bfbc276df83545e14761c3638ac6d301c9/foo -o run.py
RUN yum install net-tools telnet  bridge-utils bind-utils -y
EXPOSE 5000

CMD ["python", "run.py"]
