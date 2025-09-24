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

and use the arrow keys to navigate down to change the `server_name` as well as `root` which can be found under `location` (make sure to replace `$USERNAME`):

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
  <head>
    <title>Replace with your name!</title>
  </head>
  <body>
    Hello World!
  </body>
</html>
```

To see the result browse to `http://$USERNAME.it.pointpark.edu` (make sure to replace `$USERNAME`).
