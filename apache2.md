# Apache2 - Webserver
This is a guide to setting up a webserver on an Ubuntu Server.

## Install Apache2
1. Update packages and upgrade any packages:
    - `sudo apt update`
    - `sudo apt upgrade`
    - `sudo apt dist-upgrade`
2. Check if Apache2 is installed: `apache2 -v`
    - If not, install apache2: `sudo apt install apache2`
    - Start-up apache2: `sudo systemctl start apache2`
3. Check Apache status: `sudo /etc/init.d/apache2 status`
    ```
    ● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: active (running) since Fri 2022-09-16 03:54:32 UTC; 1 day 20h ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 12032 ExecReload=/usr/sbin/apachectl graceful (code=exited, status=0/SUCCESS)
   Main PID: 5440 (apache2)
      Tasks: 55 (limit: 19049)
     Memory: 7.6M
        CPU: 9.816s
     CGroup: /system.slice/apache2.service
             ├─ 5440 /usr/sbin/apache2 -k start
             ├─12055 /usr/sbin/apache2 -k start
             └─12056 /usr/sbin/apache2 -k start
    ```
4. Check web page on client
    - On local network, navigate to hostname of server on client's web browser.
    - Apache2 Ubuntu Default page should be displayed
    - If client cannot connect to the Apache2 Ubuntu Default page, ensure the
    firewall allows connections on ports 22 & 443
        - `sudo ufw allow 'Apache Full'`
5. Navigate to router settings and enable port forwarding for Ports 80 & 443 to
Ubuntu Server

## Get Domain
Get a domain name from a registrar of your choosing. You can also get a free
domain name from [Freenom](https://www.freenom.com/en/index.html?lang=en).

## Setup Cloudflare
Use Cloudflare to protect traffic to your domain. Setup your domain to use
Cloudflare namespace servers. Add DNS to your Server's public IP address.

## Resources
1. [Apache2 & Port Forwarding](https://www.youtube.com/watch?v=KvLj-TNXFDs)
2. [Domain Name](https://youtu.be/gsvS2M5knOw?t=226)
3. [Cloudflare](https://youtu.be/gsvS2M5knOw?t=294)
