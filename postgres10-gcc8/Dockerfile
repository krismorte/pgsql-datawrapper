from postgres:10.16

RUN apt -y update &&  apt -y upgrade
#GCC
RUN apt-get install -y wget build-essential libcurl4-openssl-dev libpq-dev pkg-config git uuid-dev libssl-dev
RUN wget http://ftp.mirrorservice.org/sites/sourceware.org/pub/gcc/releases/gcc-8.2.0/gcc-8.2.0.tar.gz && tar zxf gcc-8.2.0.tar.gz
RUN cd gcc-8.2.0 && ./contrib/download_prerequisites && ./configure --disable-multilib && make -j 4 && make install
#CMAKE
RUN apt-get install -y cmake