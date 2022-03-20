# [Jack's Homepage](https://www.jackjyq.com)

A simple personal homepage, build with bare bone HTML, CSS and JavaScript.

朴素的个人主页，基于最基础的 HTML, CSS 和 JavaScript 开发.


## Deployment

### At Server

```zsh
cd ~
git init www.jackjyq.com
cd www.jackjyq.com
git config --local receive.denyCurrentBranch updateInstead
```

### At Local

```zsh
git remote add vultr vultr:~/www.jackjyq.com
git push

find /home/jack/www.jackjyq.com -type f -exec chmod 644 {} \;
find /home/jack/www.jackjyq.com -type d -exec chmod 755 {} \;
```

### Config nginx `sudo vim /etc/nginx/conf.d/jackjyq.com.conf`

```conf
server {
        listen 80 default_server;
        server_name jackjyq.com www.jackjyq.com;
        index index.html;
        root /home/jack/www.jackjyq.com;
}
```

```zsh
sudo nginx -t
sudo systemctl restart nginx

sudo certbot --nginx
```