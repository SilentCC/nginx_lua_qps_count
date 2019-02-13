# nginx_lua_qps_count

利用lua 模块 统计qps信息的nginx 服务

### 引用

* https://github.com/zheng-ji/ngx_lua_reqstatus


* https://github.com/danday74/docker-nginx-lua

### 版本

* ubuntu : 16.04
* nginx : 1.10.3

### 用法

修改 `proxy_test.conf` 内容，加上自己的serivce

在项目文件夹下执行
```
docker build -t nginx_test:beta .
docker run -d --name nginx_test -it nginx_test:beta
```

或者直接创建自己的Dockerfile
```
FROM bigcc/nginx
COPY /your_nginx.conf /nginx/conf/nginx.conf

```
docker build ...<br/>
docker run ...

### 效果

```
curl http://127.0.0.1:4397/?domain=xxx.xxxx.xxx

Server Name key:    xxx.xxx.xxx
Seconds SinceLast:    1.0710000991821
Average Req Time Sec:    0.98439929089361
Request Count:    283
Requests Per Secs:    264.23900447452
5xx num:    0
```
