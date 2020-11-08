# Homepage Setup

## Installing Sudo

```
su
pkg install sudo
exit
```

## Installing Nginx

```
sudo pkg install nginx
sudo sysrc nginx_enable=YES
sudo service nginx start
```

Then open the nginx config file:

```
sudo ee /usr/local/etc/nginx/nginx.conf
```

and change the `server_name` as well as `root` which can be found under `location` (make sure to replace `$USERNAME`):

```
    server {
        # name of your server
        listen       80;
        server_name  $USERNAME.it.pointpark.edu;
        
        # location of the root directory
        #
        location / {
            root   /home/$USERNAME/www;
            index  index.html index.htm;
        }

        #error_page  404              /404.html;

        # redirect server error pages to the static page /50x.html
        #
        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   /usr/local/www/nginx-dist;
        }
    }
```

And restart nginx:

```
sudo service nginx restart
```

## Creating Content

Create an `index.html` file:

```
cd ~
mkdir www
ee www/index.html
```

and enter the following:

```
<!doctype html>
<html>
  <title>Replace with your name!</title>
  <body>
    Hello World!
  </body>
</html>
```

To see the result browse to `http://$USERNAME.it.pointpark.edu` (make sure to replace `$USERNAME`).
