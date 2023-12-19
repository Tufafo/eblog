---
layout: default
title: trilium配置
date: 2023-12-17
---

# <center>trilium配置</center>

## 简介

trilium是一个便捷的笔记软件，导入导出方便，可多端在线同步。

作者，Github：zadam。
翻译者：Nriver。

- 相关网站
  - [github 英文主页](https://github.com/zadam/trilium)
  - [github 中文主页](https://github.com/Nriver/trilium-translation)
  - [github 英文下载地址](https://github.com/zadam/trilium/releases)
  - [github 中文下载地址](https://github.com/Nriver/trilium-translation/releases)
  - [trilium 维基使用手册](https://trilium.netlify.app/%E6%96%87%E6%A1%A3.html)

## 服务器配置

从官网下载trilium软件包。

```bash
tar -xvf trilium-linux-x64-server-[VERSION].tar.xz
sudo mv trilium-linux-x64-server /opt/trilium
```

创建系统服务，创建 /etc/systemd/system/trilium.service 文件，输入以下内容：

```config
[Unit]
Description=Trilium Daemon
After=syslog.target network.target

[Service]
User=root
Group=root
Type=simple
ExecStart=/opt/trilium/trilium.sh
WorkingDirectory=/opt/trilium/

TimeoutStopSec=20
# KillMode=process leads to error, according to https://www.freedesktop.org/software/systemd/man/systemd.kill.html
Restart=always

[Install]
WantedBy=multi-user.target
```

启用系统服务

```bash
sudo systemctl enable --now -q trilium
```

在浏览器中输入 <服务器ip/服务器域名>+<:8080>，设置trilium密码

## TLS 配置

在数据文件夹（默认为： /home/[user]/.local/share/trilium-data ）下的 config.ini 文件中，修改以下配置项：

```config
[Network]

# trilium服务器端口
port=8080


# 是否启用ssl
https=true

# 证书位置
certPath=/[username]/.acme.sh/[hostname]/fullchain.cer
keyPath=/[username]/.acme.sh/[hostname]/example.com.key
```

◎重启triilum

```bash
systemctl restart trilium
```

## 参考


- [Trilium: Data directory](https://github.com/zadam/trilium/wiki/Data-directory)
- [Trilium: TLS Configuration](https://github.com/zadam/trilium/wiki/TLS-configuration)
- [Trilium: Packaged server installation](https://github.com/zadam/trilium/wiki/Packaged-server-installation)
