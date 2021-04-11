from postgres:12.6

RUN apt -y update &&  apt -y upgrade
RUN apt-get install -y git wget cmake make gcc uuid-dev
#Elastic Wrapper
RUN apt-get install -y python3 python3-distutils python3-dev libpython3-dev python3-pip 
RUN apt-get install -y pgxnclient
RUN apt install -y postgresql-server-dev-12
RUN pgxn install multicorn
#RUN apt-get install -y postgresql-11-python-multicorn 
RUN pip3 install "elasticsearch>=7,<8"
RUN pip3 install pg_es_fdw
#MySQL
RUN apt-get install -y postgresql-12-mysql-fdw
#ClickHouse
RUN apt-get install -y build-essential libcurl4-openssl-dev libpq-dev pkg-config
RUN git clone https://github.com/adjust/clickhouse_fdw.git && cd clickhouse_fdw && mkdir build && cd build && cmake .. && make && make install
#Mongo
RUN apt-get install -y libmongoc-dev  libbson-dev 
RUN git clone https://github.com/EnterpriseDB/mongo_fdw.git --recursive && cd mongo_fdw && sed -i "s|cmake3|cmake|" autogen.sh && ./autogen.sh --with-master && make -f Makefile.meta && make -f Makefile.meta install
