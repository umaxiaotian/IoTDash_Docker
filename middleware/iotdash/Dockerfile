FROM oraclelinux:8.6
#Node Install
RUN curl -sL https://rpm.nodesource.com/setup_16.x | bash -
RUN dnf -y install nodejs
RUN npm install -g yarn

#mosquitto Install
RUN dnf -y install epel-release
RUN dnf makecache --refresh
RUN dnf -y install mosquitto
RUN systemctl enable mosquitto

#FastAPI Install
WORKDIR /tmp
RUN dnf -y update
RUN dnf -y install \ 
    kernel-devel \
    kernel-headers \
    gcc-c++ \
    patch \
    libffi-devel \
    autoconf \
    automake \
    make \
    libtool \
    bison \
    tk-devel \
    zip \
    wget \
    tar \
    gcc \
    zlib \
    zlib-devel \
    bzip2 \
    bzip2-devel \
    readline \
    readline-devel \
    sqlite \
    sqlite-devel \
    openssl \
    openssl-devel \
    git \
    gdbm-devel
RUN wget https://www.python.org/ftp/python/3.8.0/Python-3.8.0.tgz
RUN tar xzvf Python-3.8.0.tgz
WORKDIR ./Python-3.8.0
RUN ./configure --with-threads
RUN make install
RUN pip3 install --upgrade pip
RUN pip3 install --upgrade setuptools
RUN pip3 install fastapi uvicorn python-multipart python-jose peewee python-dotenv psycopg2-binary>=2.8.6
#WORKDIR /api
# CMD ["uvicorn", "main:app", "--reload", "--host", "0.0.0.0", "--port", "8000"]