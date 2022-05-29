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
WORKDIR /etc/mosquitto

WORKDIR /app
EXPOSE 3000
