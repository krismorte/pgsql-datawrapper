from postgres:10.16

RUN apt update
#Elastic Wrapper
RUN apt-get install -y python python-pip
RUN apt-get install -y postgresql-10-python-multicorn 
RUN pip install "elasticsearch>=7,<8"
RUN pip install pg_es_fdw
#MySQL
RUN apt-get install -y postgresql-10-mysql-fdw
#GCC
RUN apt-get install -y wget build-essential libcurl4-openssl-dev libpq-dev pkg-config git uuid-dev libssl-dev
RUN wget http://ftp.mirrorservice.org/sites/sourceware.org/pub/gcc/releases/gcc-8.2.0/gcc-8.2.0.tar.gz && tar zxf gcc-8.2.0.tar.gz
RUN cd gcc-8.2.0 && ./contrib/download_prerequisites && ./configure --disable-multilib && make -j 4 && make install
#CMAKE
RUN wget https://github.com/Kitware/CMake/releases/download/v3.20.1/cmake-3.20.1.tar.gz && tar zxf cmake-3.20.1.tar.gz
RUN cd cmake-3.20.1 && ./bootstrap && make -j$(nproc) && make install
