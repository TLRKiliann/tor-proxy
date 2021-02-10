# tor-proxy
install tor proxy on linux and raspberry pi 400

sudo apt install tor

sudo systemctl status tor

sudo systemctl status tor@default.service

Configuration for torrc :
sudo nano /etc/tor/torrc

sudo systemctl restart tor

sudo systemctl restart tor@default.service

The 2 addr must be different :

wget -qO - https://wwww.icanhazip.com

torsocks wget -qO - https://wwww.icanhazip.com

sudo systemctl disable tor

Browser firefox configuration :

Network settings : settings

Manual proxy configuration

SOCKS host : 127.0.0.1  port : 9050

Proxy DNS when using SOCKS v5
