# Why?
Easy to build server
One login to all Service

# Setup
## install
Follow offical instructions HTTPS approach or git .sh approach
## setup site
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
