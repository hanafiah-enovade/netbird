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

- Download docker, docker compose installation scripts

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

# Step 3: Netbird Installation

Reference: https://docs.netbird.io/selfhosted/selfhosted-quickstart

- Download Netbird installation scripts

```
curl -sSLO https://github.com/netbirdio/netbird/releases/latest/download/getting-started-with-zitadel.sh
```

- Check the script
```
cat getting-started-with-zitadel.sh
```
- Run the script. (**Note**: Replace tunnel.cloud-connect.asia with your domain name created in Step 1)
```
export NETBIRD_DOMAIN=tunnel.cloud-connect.asia
bash getting-started-with-zitadel.sh
```
- The following are the outcome example
```
       You can access the NetBird dashboard at https://tunnel.cloud-connect.asia:443
       Login with the following credentials:
       Username: admin@tunnel.cloud-connect.asia
       Password: ZQeOOByV9T0pGViQav2Km/cuwRWtSWwbehA3ZmJEJtY@
```

## Step 3.1: Verifying Netbird Installation
- Access to https://tunnel.cloud-connect.asia:443 with the following example info
```
	Username: admin@tunnel.cloud-connect.asia
	Password: ZQeOOByV9T0pGViQav2Km/cuwRWtSWwbehA3ZmJEJtY@
```
<img src="https://code.cloud-connect.asia/researchproject/networking/netbird/uploads/856334f2b1318290978af4abce128488/image.png" width=400>

- Click **Skip**

<img src="https://code.cloud-connect.asia/researchproject/networking/netbird/uploads/e471f0e02da81023c21982d7b45ed3e8/image.png" width=400>

- Change to New Password if required

## Step 3.2: Verifying Zitadel Configuration
- Access to Zitadel IAM https://tunnel.cloud-connect.asia/ui/console
```
	Username: admin@tunnel.cloud-connect.asia
	Password: ZQeOOByV9T0pGViQav2Km/cuwRWtSWwbehA3ZmJEJtY@
```

