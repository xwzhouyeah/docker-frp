FROM ubuntu:16.04

LABEL AUTHOR="xwzhou@yeah.net"

ENV FRP_VERSION=0.16.0

RUN apt update \
&& apt install -y wget

WORKDIR /tmp
RUN set -x \
&& wget https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_amd64.tar.gz \
&& tar -zxf frp_${FRP_VERSION}_linux_amd64.tar.gz \
&& mv frp_${FRP_VERSION}_linux_amd64 /frp \
&& mkdir -p /frp \
&& apt remove -y wget \
&& apt autoremove -y \
&& rm -rf /var/lib/apt/lists/*

COPY frps.ini /frp/frps.ini

WORKDIR /frp
ENTRYPOINT /frp/frps -c /frp/frps.ini

EXPOSE 7000 7500 80 433
EXPOSE 7001 7002 7003 7004 7005 7006 7007 7008 7009 7010
