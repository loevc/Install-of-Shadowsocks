# Install-of-Shadowsocks
This  is  a  text file . In order to remember how to use the shadowsocks 

## why use the google ?
I search long time for a method that can bring me the google.com
Last month , i find it .
Google help me see the more science knowlarge , i just learn more by wished.

## waht i get in the github 
Search "shadowsocks" ,I get the tools from [Here](https://github.com/shadowsocks/shadowsocks-windows).

## tools
pip
vim
shadowsocks

## environmnet
centos 7.7   
kernel 5.8.1 (That is second version by update)

## The process how to install & use
```pip install shadowsocks
vim /etc/shadowsocks.json 
```
shadowsocks.json
```
{
"server":"0.0.0.0",
"server_port":xxxx,   # choose a  port from 1025-65535
"local_port":1080,
"password":"**********",  # set a passwd stronger
"timeout":600,
"method":"aes-256-cfb" #  recommand use  chacha20-ietf-poly1305
}
```

```
vim /etc/supervisord.conf
```
supervisord.conf
```
[program:shadowsocks]
command=ssserver -c /etc/shadowsocks.json
autostart=true
autorestart=true
user=root
log_stderr=true
logfile=/var/log/shadowsocks.log   #for  different kernel，the file maybe not exist
```
```
vim /etc/rc.local
```

the command reboot can use "**init6**" or  "**reboot**"

```
ssserver -c /etc/shadowsocks.json -d start
```



test bbr 
```
sysctl net.ipv4.tcp_congestion_control
sysctl net.ipv4.tcp_available_congestion_control
```


i found a thing that the server will go slowly by the system running away.
reboot the system will solve this problem , maybe it products a lot caches.
how to reboot nobody ?
i search a method 
use the crontab

let 
```
cat /etc/crontab

```
the first open it  ,
there will have a doc to tell you this's format

```
vim /etc/crontab
```
to add below cotent

```
15 04 * * 1 root reboot
20 04 * * 1 root /usr/local/bin/ssserver -c /etc/shadowsocks.json -d start
```

then to reboot the server crontab
```
systemctl restart crond.service
```
the  crond  have other parameter that "reload  start"
