FROM alpine
MAINTAINER Usaki
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories && \
    apk --update add wget tzdata && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    wget -P /usr/local https://github.com/opq-osc/OPQ/releases/download/v6.7.5/OPQBot_6.7.5_linux_amd64.tar.gz && \
    tar -xf /usr/local/OPQBot_6.7.5_linux_amd64.tar.gz -C /usr/local && \
    apk del tzdata wget && rm -f /usr/local/OPQBot_6.7.5_linux_amd64.tar.gz
WORKDIR /usr/local/OPQBot_6.7.5_linux_amd64
CMD ["./OPQBot"]
