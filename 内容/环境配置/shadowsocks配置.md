---
layout: default
title: shadowsocks配置
date: 2023-12-17
---

# <center>shadowsocks配置</center>

## 简介



shadowsocks，网络代理工具，可翻墙。

- 相关网站：
	- [Github: shasowsocks](https://github.com/shadowsocks) 
	- [Shadowsocks 官网](https://shadowsocks.org/)
	- [维基百科： shadowsocks](https://zh.wikipedia.org/zh-hans/Shadowsocks)



## 服务器配置



## ubuntu22-server snap



**◎ 命令行安装shadowsocks-libev**

```bash
sudo snap install shadowsocks-libev
sudo mkdir -p /var/snap/shadowsocks-libev/common/etc/shadowsocks-libev
sudo vim /var/snap/shadowsocks-libev/common/etc/shadowsocks-libev/config.json
```

在文件 **/var/snap/shadowsocks-libev/common/etc/shadowsocks-libev/config.json** 中，输入以下内容：

```json
{
    "server":"服务器地址",
    "server_port":"服务器端口",
    "local_port":1080,
    "password":"密码",
    "timeout":60,
    "method":"aes-256-gcm",
    "mode":"tcp_and_udp",
    "fast_open":false
}
```

注意【服务器地质】【服务器端口】【密码】【加密方式】等参数需要更换为具体环境配置。



**◎ 配置系统服务**

创建 **/etc/systemd/system/shadowsocks-libev-local@.service** 文件，输入以下内容：

```config
[Unit]
Description=Shadowsocks-Libev Custom Client Service for %I
After=network-online.target

[Service]
Type=simple
ExecStart=/usr/bin/snap run shadowsocks-libev.ss-local -c /var/snap/shadowsocks-libev/common/etc/shadowsocks-libev/%i.json
Restart=on-failure
RestartSec=15

[Install]
WantedBy=multi-user.target
```


**◎ 启动系统服务**

```bash
sudo systemctl enable shadowsocks-libev-local@config
sudo systemctl start shadowsocks-libev-local@config
```


## 客户端配置

### ubuntu22-desktop


◎安装客户端GUI

```
snap install shadowsocks-electron
```

启动 shadowsocks-electron ，输入与服务器相应的配置。



◎配置firefox浏览器代理

设置>代理，进行如下操作：

1. 选择 **手动配置**

2. socks5主机设置为：127.0.0.1 ，端口设置为： 1080



### 其它系统



- 客户端下载地址
	- [windows](https://github.com/shadowsocks/shadowsocks-windows/releases)
	- [android](https://github.com/shadowsocks/shadowsocks-android/releases)



## 参考

[Debian & Ubuntu 上使用 shadowsocks-libev 客户端](https://blog.chaos.run/dreams/debian-shadowsocks-libev-client/index.html)
