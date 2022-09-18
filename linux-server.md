# Linux Server - Guide
This is a guide to setup a Linux home server and tips/adive to secure it.

## Automatic Updates
1. Check for updates: `sudo apt update`
2. Run any available updates: `sudo apt upgrade`
3. Run dist-upgrade: `sudo apt dist-upgrade`
4. Install *unattended-upgrades*: `sudo apt install unattended-upgrades`
5. Set priority for *unattended-upgrades*: `sudo dpkg-reconfigure --priority=low unattended-upgrades`
    - Select *yes* on menu 

## Limit User Accounts
Place limits and restrictions on your users. Disable root login.
1. Create user account, if none exist: `sudo adduser <USERNAME>`
2. Add newly creted user to `sudo` group: `sudo usermod -aG sudo <USERNAME>`
3. Use non-root account for most work

## Public/Private Keys
User public/private keys to authenticate & log into server instead of password.
1. Check if `~/.ssh` directory exists
    - If not, create it with `mkdir ~/.ssh && chmod 700 ~/.ssh`
2. On the client-side, create public/private keys: `ssh-keygen -b 4096`
3. Send public to server
    - For Windows, use: `scp $env:USERPROFILE/.ssh/id_rsa.pub <USERNAME>@<HOSTNAME>:~/.ssh/authorized_keys`
    - For Linux, use: `ssh-copy-id <USERNAME>@<HOSTNAME>`
    - For Mac, use: `scp ~/.ssh/id_rsa.pub <USERNAME>@<HOSTNAME>:~/.ssh/authorized_keys`

## Limit Login & Harden SSH
### Edit sshd config file
1. Edit sshd config file: `sudo vi /etc/ssh/sshd_config`
2. Change SSH `Port` from default `22` to a different unused port
3. Change `AddressFamily` from `any` to use `inet` IPv4 only
4. Change `PermitRootLogin` to `no`
5. Change `PasswordAuthentication` to `no`
6. Write to file and save changes

### Apply config changes
1. Run `sudo systemctl restart sshd` to restart ssh daemon

### Test changes
1. Open new terminal on client
2. Run `ssh <USERNAMR>@<HOSTNAME>`
    - Connection on port 22 should be refused
3. Run `ssh <USERNAME>@<HOSTNAME> -p <PORT>` with the port set in config

## Setup Firewall
1. Check for open ports on Server: `sudo ss -tupln`
2. Check if `ufw` is installed on server: `ufw --version`
    - If not, install `ufw`: `sudo apt install ufw`
3. Check firewall status: `sudo ufw status`
4. Allow ssh port on firewall: `sudo ufw allow <PORT>`
    - Repeat for other desired ports
5. Enable firewall: `sudo ufw enable`

### Disable pings to server
1. Edit `sudo vi /etc/ufw/before.rules`
2. Find section with the heading: `# ok icmp codes for INPUT`
3. Add this line right below the heading: `-A ufw-before-input -p icmp --icmp-type echo-request -j DROP`
4. Write and save to file
5. Reload firewall: `sudo ufw reload`

## Resource
1. [Secure Linux Server - NetworkChuck](https://www.youtube.com/watch?v=ZhMw53Ud2tY)
