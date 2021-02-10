# tor-proxy

>>Install tor proxy on linux and raspberry pi 400

Installation:
>sudo apt install tor

>sudo systemctl status tor

>sudo systemctl status tor@default.service

Configuration for torrc :
>sudo nano /etc/tor/torrc

SOCKSPort 9050 
SOCKSPort 192.168.X.Y:9999 
SOCKSPolicy accept 192.168.0.0/16 
RunAsDaemon 1 
DataDirectory /var/lib/tor 

>sudo systemctl restart tor

>sudo systemctl restart tor@default.service

The 2 addr must be differents :

>wget -qO - https://wwww.icanhazip.com

>torsocks wget -qO - https://wwww.icanhazip.com

To avoid a loopback when Linux start :
>sudo systemctl disable tor

Browser firefox configuration :

Click on --> Network settings : settings

Click on --> Manual proxy configuration

Enter --> SOCKS host : 127.0.0.1  port : 9050

Click on --> Proxy DNS when using SOCKS v5

To verify your installation look at with :
>ss -nlt

>watch netstat -pute
