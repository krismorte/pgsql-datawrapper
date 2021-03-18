from postgres:10.16

RUN apt update
#Elastic Wrapper
RUN apt-get install -y python python-pip
RUN apt-get install -y postgresql-10-python-multicorn 
RUN pip install "elasticsearch>=7,<8"
RUN pip install pg_es_fdw
#MySQL
RUN apt-get install -y postgresql-10-mysql-fdw
