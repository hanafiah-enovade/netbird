[[_TOC_]]

# Step 1: Environment Readiness

- Create a VM instance with min 1VCPU 2GB RAM
- Create A record i.e tunnel.cloud-connect.asia with the VM IP address
- Access to the VM and update the OS

```
ssh root@tunnel.cloud-connect.asia
apt update && apt upgrade -y
sudo reboot
```
- Optional steps: create admin user

```
ssh root@tunnel.cloud-connect.asia
adduser pentadbir
usermod -aG sudo pentadbir
cp -r .ssh /home/pentadbir/
chown -R pentadbir:pentadbir /home/pentadbir/
exit
```

# Step 2: Docker Installation & Configuration

- Copy docker, docker compose installation scripts

```
wget -O install-docker.sh https://gitlab.com/bmcgonag/docker_installs/-/raw/main/install_docker_nproxyman.sh?ref_type=heads
```

- Change the file as executable
```
chmod +x install-docker.sh
```

- Install docker

```
./install-docker.sh
# Select 4, Docker-CE to yes and Docker-compose to yes
```
- The following are the outcome example

```
We can install Docker-CE, Docker-Compose, NGinX Proxy Manager, and Portainer-CE.
Please select 'y' for each item you would like to install.
NOTE: Without Docker you cannot use Docker-Compose, NGinx Proxy Manager, or Portainer-CE.
       You also must have Docker-Compose for NGinX Proxy Manager to be installed.


Docker-CE (y/n): y
Docker-Compose (y/n): y
NGinX Proxy Manager (y/n): n
Navidrome (y/n): n
Portainer-CE (y/n): n
Remotely - Remote Desktop Support (y/n): n
Guacamole - Remote Desktop Protocol in the Browser (y/n): n
```

- Verify docker installation

```
docker ps
```

7. SSH again using > ssh pentadbir@157.245.48.123 or ssh pentadbir@FQDN

<img src="https://code.cloud-connect.asia/msp/akademi-cloud-connect/training-modules/infrastruktur-moden/uploads/cfbb3cc38911e13ab4be4959294005aa/image.png" width=700>
