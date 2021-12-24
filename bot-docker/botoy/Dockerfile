FROM python:3.8-alpine
MAINTAINER Usaki
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories && \
    apk --update --no-cache add tzdata g++ gcc libxslt-dev jpeg-dev linux-headers && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    pip install -i https://mirrors.huaweicloud.com/repository/pypi/simple --upgrade pip && \
    pip install --no-cache-dir -i https://mirrors.huaweicloud.com/repository/pypi/simple botoy httpx python-socketio==4.6.1 python-engineio==3.14.2 websocket-client loguru click aiohttp prettytable apscheduler pydantic colorama qrcode pillow python_dateutil requests py-cpuinfo psutil ujson && \
    mkdir /usr/local/botoy && apk del tzdata g++ gcc libxslt-dev jpeg-dev linux-headers
ADD data/ /usr/local/botoy/
WORKDIR /usr/local/botoy
CMD ["botoy","run"]
