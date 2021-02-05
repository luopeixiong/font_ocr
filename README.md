# font_ocr



docker-compose up -d





测试

curl -X POST \
  http://119.29.27.234:8088/ocr \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: a4bb25a3-15a1-50d0-612a-8f804df49c14' \
  -d '{"url": "https://vfile.meituan.net/colorstone/f0a30a4dda64b4f8f344858115f54fc92296.woff", "content": ""}'
