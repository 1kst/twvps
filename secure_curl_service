# 创建服务

```bash
sudo nano /etc/nginx/sites-available/secure_curl_service
```

# 代码：

```nginx
server {
    listen 192.168.5.12:10086;  # 修改为你的服务器IP和端口
    server_name 192.168.5.12;

    root /var/www/html;  # Web根目录

    location /hwVpGSlL5KWa {
        fastcgi_pass unix:/var/run/fcgiwrap.socket;
        include /etc/nginx/fastcgi_params;
        fastcgi_param SCRIPT_FILENAME /var/www/cgi-bin/execute_curl.sh;
    }

    # 默认禁止其他路径访问
    location / {
        return 403;
    }
}
```

# 创建 CGI 脚本目录

```bash
sudo mkdir -p /var/www/cgi-bin
```

```bash
sudo chmod 755 /var/www/cgi-bin
```

```bash
sudo nano /var/www/cgi-bin/execute_curl.sh
```

# 代码：

```bash
#!/bin/bash
echo "Content-type: text/plain"
echo ""

# 执行 curl 1.1.1.1 命令
curl 1.1.1.1
```

# 保存脚本并赋予执行权限：

```bash
sudo chmod +x /var/www/cgi-bin/execute_curl.sh
```

# 重启或重新加载 Nginx

```bash
sudo systemctl reload nginx
```
