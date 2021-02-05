# font_ocr

# css字体反混淆一键部署方案

git图片显示有问题 
可以看这 [链接](https://www.jianshu.com/writer#/notebooks/49400538/notes/83534700/preview)

提供api 
    - url     反混淆文本使用的woff 链接
    - content 需要反混淆的文本
```
api
curl -X POST \
  http://119.29.27.234:8088/ocr \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: a4bb25a3-15a1-50d0-612a-8f804df49c14' \
  -d '{"url": "https://vfile.meituan.net/colorstone/f0a30a4dda64b4f8f344858115f54fc92296.woff", "content": ""}'

```





配置阿里镜像源


```
sudo mkdir -p /etc/docker

sudo tee /etc/docker/daemon.json <<-'EOF'

{

  "registry-mirrors": ["https://uxk0ognt.mirror.aliyuncs.com"]

}

EOF

sudo systemctl daemon-reload

sudo systemctl restart docker
```


本地部署

```
# 安装docker 
# 安装docker-compose
# pip3 install docker-compose
# 进入docker-compose.yaml所在目录
# 本地化部署
docker-compose up -d
```


案例

提取混淆文字 
![猫眼电影](./WeChatcdd5a362ebe748bdb421d72690e230d2.png)
提取字体url //vfile.meituan.net/colorstone/f0a30a4dda64b4f8f344858115f54fc92296.woff
![猫眼字体](./WeChat266ab2365b961ab91d61f7bb85ad9c84.png)


测试
```
url : http://119.29.27.234:8088/ocr
jsonData:
    - content: 
    - url: https://vfile.meituan.net/colorstone/f0a30a4dda64b4f8f344858115f54fc92296.woff
```
curl 测试
```
curl -X POST \
  http://119.29.27.234:8088/ocr \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: a4bb25a3-15a1-50d0-612a-8f804df49c14' \
  -d '{"url": "https://vfile.meituan.net/colorstone/f0a30a4dda64b4f8f344858115f54fc92296.woff", "content": ""}'

```

![识别结果](./WeChat2379f547c470d509a4b25b2e503f446d.png)