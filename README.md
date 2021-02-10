# tor-proxy

Install tor proxy on linux and raspberry pi 400

# Installation :
>sudo apt install tor

To verify installation use cmd :
>sudo systemctl status tor

>sudo systemctl status tor@default.service

# Configuration for torrc :
>sudo nano /etc/tor/torrc

SOCKSPort 9050 \
*Replace XY by your IP addr (ifconfig)* \
SOCKSPort 192.168.X.Y:9977 \
SOCKSPolicy accept 192.168.X.0/16 \
RunAsDaemon 1 \
DataDirectory /var/lib/tor 

Save and close torrc file

Restart daemon :
>sudo systemctl restart tor
Restart service :
>sudo systemctl restart tor@default.service

# The 2 addr (PUBLIC IP) must be differents :

>wget -qO - https://wwww.icanhazip.com

>torsocks wget -qO - https://wwww.icanhazip.com

To avoid a loop error when Linux start :
>sudo systemctl disable tor

# Browser firefox configuration :

Click on --> Network settings : settings

Click on --> Manual proxy configuration

Enter --> SOCKS host : 127.0.0.1  port : 9050

Click on --> Proxy DNS when using SOCKS v5

# To verify your installation use cmd :
>ss -nlt

>watch netstat -pute
