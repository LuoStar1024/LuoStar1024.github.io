---
title: Git设置SSH和Https代理
author: 落星
tags:
  - Git
categories:
  - 其他技术
date: 2026-04-04 11:49:18
---
先假设本地代理端口：7079

## HTTPS 方式代理

### 全局代理

设置代理配置：

```
# 设置 HTTP 代理
git config --global http.proxy http://127.0.0.1:7079

# 设置 HTTPS 代理
git config --global https.proxy http://127.0.0.1:7079
```

验证是否成功：

```
git config --get http.proxy
git config --get https.proxy
```

取消代理配置：

```
git config --global --unset http.proxy
git config --global --unset https.proxy
```

### 特点网站代理

例如github：

```
# 设置代理
git config --global http.https://github.com.proxy http://127.0.0.1:7079

# 是否生效
git config --global --get-regexp proxy

# 取消代理
git config --global --unset http.https://github.com.proxy
```

## SSH 方式代理

编辑 `\x7e/.ssh/config`，添加以下内容。没有该文件就新建，无后缀名。

### 如果 `7079` 是 HTTP 代理

```sshconfig
Host github.com
  HostName ssh.github.com
  Port 443
  User git
  ProxyCommand connect.exe -H 127.0.0.1:7079 %h %p
```

### 如果 `7079` 是 SOCKS5 代理

如果软件上显示为混合代理，也使用这个。

```sshconfig
Host github.com
  HostName ssh.github.com
  Port 443
  User git
  ProxyCommand connect.exe -S 127.0.0.1:7079 %h %p
```

### 测试 SSH

```
ssh -T git@github.com
```
