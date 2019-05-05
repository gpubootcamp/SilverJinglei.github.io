# Why?
Easy to build server
One login to all Service

# Setup
## install
Follow offical instructions HTTPS approach or git .sh approach

## setup site

> never use the tip domain name or suggestions. press 'none' => access admin page directly. config:
```
SERVER_USER=sandstorm
PORT=6080
MONGO_PORT=6081
BIND_IP=0.0.0.0
BASE_URL=http://GPUSW-ubuntu16-01:6080
WILDCARD_HOST=*.GPUSW-ubuntu16-01:6080
UPDATE_CHANNEL=dev
ALLOW_DEV_ACCOUNTS=false
SMTP_LISTEN_PORT=25
```

```shell
sudo sandstorm admin-token

https://bootcamp.sandcats.io/setup/token/xxxxx
```

Issue: Cannot access above token page <= cannot find the domain name
> Cannot finde the domain name 'bootcamp.sandcats.io', it should be point to your localhost (127.0.0.1)
> @intranet approach:  find DNS to update
> @hosts approach:     
> 1. sudo vim /etc/hosts
> 2. insert to bottom
> ```
> 127.0.0.1   bootcamp.sandcats.io
> ```
> 3. sudo /etc/init.d/networking restart

Issue: Cannot load grain
> https://docs.sandstorm.io/en/latest/administering/faq/#how-do-i-use-sandstorm-with-an-internal-ip-address
```
SERVER_USER=sandstorm
PORT=6080
MONGO_PORT=6081
BIND_IP=0.0.0.0
BASE_URL=http://192.168.6.114.xip.io:6080
WILDCARD_HOST=*.192.168.6.114.xip.io:6080
UPDATE_CHANNEL=dev
ALLOW_DEV_ACCOUNTS=false
SMTP_LISTEN_PORT=25
#SANDCATS_BASE_DOMAIN=sandcats.io
#HTTPS_PORT=443
```
> BASE_URL use http, non-https
