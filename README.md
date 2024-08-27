# Firewall-for-proxy-server-Setup-docs
The best way to fool-proof and secure your BungeeCord server is using a firewall in order to prevent access to them at all from the outside world. By default, most Linux distros come preinstalled with the easy to use iptables. Once you have everything set up you can activate this firewall with the command below. Replace $BUNGEE_IP with the IP of the server running BungeeCord, if your Minecraft server(s) and Bungeecord are on the same physical server, this IP will be 127.0.0.1. Replace $SERVER_PORT with the port of your Minecraft server.

**Please note that all commands must be run as root. (E.g. with sudo)**

## Installing iptables
Installation of the iptables software to your machine is fairly straightforward depending on your distribution of Linux. 
Note that Windows Server does not come with iptables pre-installed.

 **RedHat/CentOS Distributions**

     
     yum install iptables
   

 **Debian/Ubuntu Distributions**
 
      apt-get install iptables


## Firewalling with iptables

      iptables -I INPUT ! -s $BUNGEE_IP -p tcp --dport $SERVER_PORT -j DROP

Alternatively if you have multiple Minecraft servers running instead of writing a rule for each server and its port you can use the following command to add a port range which will be blocked by the firewall. Replace $START_PORT and $END_PORT with your desired port range, don't forget the colon in between.
