# FE2AS

菜鸡前端试图了解一点后端知识

## nginx

我主要想学的，想多了解一点的肯定先是 `nginx`。其实也确实了解了一些 `nginx` 。

比如：

`nginx` 读音为 `engine-x` /’endʒɪneks/

配置文件路径：
`/etc/nginx/sites-available/defalut`

默认展示文件路径：
`/var/www/html`

```bash
# default 内的 nginx 基本配置文件
server {
	listen 80 default_server;
	listen [::]:80 default_server;
	# ngnix 默认根目录
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
