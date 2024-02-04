# Let's Encrypt

## Prerequisites

- You have installed `sudo` and `nginx`.
- You have configured `nginx` to serve from `www` in your home directory.
- See also [this tutorial](homepage-setup).

## Installing

```
sudo pkg install py38-certbot
```

Note: you might have to update the Python version to a more recent one, e.g., change `py38-certbot` to `py39-certbot`.

## Configuring

```
sudo certbot certonly --noninteractive --email mvoortman@pointpark.edu --agree-tos --webroot --webroot-path /home/mvoortman/www --domain mvoortman.it.pointpark.edu
```

Note: make sure to replace all the usernames with your own (3 in total).

Make the following changes in your Nginx configuration file after running `sudo ee /usr/local/etc/nginx/nginx.conf`:

```
...
http {
    ...

    # new server section to redirect all traffic to https
    server {
        listen 80 default_server;
        server_name _;
        return 301 https://$host$request_uri;
    }

    # this is the original server section now using https
    server {
        # comment or remove the next line
        #listen       80;
        # now enable https
        listen       443 ssl;
        server_name  localhost;
        
        ssl_certificate /usr/local/etc/letsencrypt/live/mvoortman.it.pointpark.edu/fullchain.pem;
        ssl_certificate_key /usr/local/etc/letsencrypt/live/mvoortman.it.pointpark.edu/privkey.pem;
        ssl_trusted_certificate /usr/local/etc/letsencrypt/live/mvoortman.it.pointpark.edu/chain.pem;
        
        ...
    }
    ...
}
```

And restart Nginx:

```
sudo service nginx restart
```

After this try browsing to your homepage and then it should automatically redirect you to https.

To make sure the certificates keep working in the future, open the crontab with `sudo ee /etc/crontab` and add the following line at the end to automatically renew the certificates:

```
13 3 * * * root /usr/local/bin/certbot renew --post-hook "service nginx restart"
```

If you want to proxy a project to node you can add the following few lines to `nginx.conf`:

```
...
http {
    ...
    server {
        ...
        location /project/ {
            proxy_pass http://127.0.0.1:3000/;
        }
        ...
    }
    ...
}
```
