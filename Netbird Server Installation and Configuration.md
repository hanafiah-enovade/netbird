[[_TOC_]]

# Step 1: Environment Readiness

1. Create a VM instance with min 1VCPU 2GB RAM
2. Create A record I.e tunnel.cloud-connect.asia with the VM IP address
3.  ssh root@tunnel.cloud-connect.asia  
4. Run > apt update && apt upgrade -y
5. Reboot VM > sudo reboot
6. Create admin user 
    1. > adduser pentadbir
    2. > usermod -aG sudo pentadbir
    3. > cp -r .ssh /home/pentadbir/
    4. > chown -R pentadbir:pentadbir /home/pentadbir/
    5. > exit
7. SSH again using > ssh pentadbir@157.245.48.123 or ssh pentadbir@FQDN

