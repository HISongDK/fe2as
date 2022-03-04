# FE2AS

菜鸡前端试图了解一点后端知识

## nginx

我主要想学的，想多了解一点的肯定先是 `nginx`。其实也确实了解了一些 `nginx` 。

比如：

`nginx` 读音为 `engine-x` /’endʒɪneks/

配置文件路径：
`/etc/nginx/sites-available/default`

默认展示文件路径：
`/var/www/html`

```bash
# default 内的 nginx 基本配置文件
server {
	listen 80 default_server;
	listen [::]:80 default_server;
	# nginx 默认根目录
	root /var/www/html;
	# 默认寻找的文件
	index index.html index.htm index.nginx-debian.html;
	server_name _;
	location / {
    # 代理转发 将 nginx 的默认 80 端口代理为本地 3000 端口运行的服务
    # 这么一看确实是不知道转发代理的意义在哪
		proxy_pass http://127.0.0.1:3000/;
	}
}
```

关于 `gzip` 压缩，默认配置是开启的。
所在文件路径是：`/etc/nginx/nginx.conf`

## Security

安全问题很是重要

- SSH
- FireWall
- Update
- VPN

## http

> Stand for: **hypertext transport protocol**

### headers

common headers

| key             | value                             |
| --------------- | --------------------------------- |
| User-agent      | The requesting device type        |
| Accept          | What the device will handle       |
| Accept-language | Browser languages                 |
| Content-type    | The type of media                 |
| _Set-cookie_    | Sets stateful information         |
| X-              | Typically used for custom headers |
