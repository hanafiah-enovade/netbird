# Adding Machines to Network
- Reference: https://docs.netbird.io/how-to/add-machines-to-your-network
- Use setup keys to run automated deployments and add machines to your network at scale

## Step 1.1: Creating Setup keys
- Access to https://tunnel.cloud-connect.asia:443, from the menu select **Setup Keys**, and click **Add key**

<img src="https://code.cloud-connect.asia/researchproject/networking/netbird/uploads/c4ead45bef225073f3346b73e8da6fce/image.png" >


- Enter relevant info as per the following screenshot, and click **Create key**

<img src="https://code.cloud-connect.asia/researchproject/networking/netbird/uploads/a0b8dbbf5f821b338a864dd1ffae1fa6/image.png" width=400>

- Copy and store the key, click **Done**

<img src="https://code.cloud-connect.asia/researchproject/networking/netbird/uploads/adc5863836ca576c62a47d756b81a071/image.png" width=400>

## Step 1.2: Hosts file configuration

- Access to VM client via SSH, for Linux, change the hosts file
```
sudo nano /etc/hosts
```
- Commented the following entry and save the hosts file
```
#127.0.1.1 secure-tunnel-server secure-tunnel-server
127.0.0.1 localhost
```

## Step 4.3: 
