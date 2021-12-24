基于botoy7.11版本,python:3.8-alpine基础镜像进行制作
Dockerfile已给出,有需要可以自行修改构建(gn不会懂的,gn怎么可能懂呢,gn只会白嫖)


启动步骤：
1.修改当前目录 data/botoy.json 配置文件信息
注意host这一行的IP地址需要改为宿主机IP(127.0.0.1就变成容器内部IP了)
OPQBot端口如果有变化就跟着改,默认保持为8888端口即可


2.导入镜像
这回镜像构建比较麻烦,提前放在当前目录了,导入即可
docker load -i image.tar.gz


3.命令

启动botoy(配置opqbot-docker使用更加):
docker run -d --name botoy -v $(pwd)/data:/usr/local/botoy botoy:7.11

重启botoy:
docker restart botoy

or

docker rm -f botoy && docker run -d --name botoy -v $(pwd)/data:/usr/local/botoy botoy:7.11

重启比较慢可以选择下面那种

查看日志:
docker logs -f botoy


镜像默认已经集成以下依赖库(如有其他需要请自行解决,gn怎么连这都解决不了呢): 
botoy
httpx
python-socketio==4.6.1
python-engineio==3.14.2
websocket-client
loguru
click
aiohttp
prettytable
apscheduler
pydantic
colorama
qrcode
pillow
python_dateutil
requests
py-cpuinfo
psutil
ujson

默认自带sysinfo插件,需要添加其他插件请放至 data/plugins 目录下
之后通过 docker restart botoy 重启botoy,
查看日志是否有异常 docker logs -f botoy
