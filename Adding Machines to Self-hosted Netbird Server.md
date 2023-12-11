[[_TOC_]]

# Adding Machines to Self-hosted Netbird Server
- Pre-requisite:
```
- Netbird server - https://code.cloud-connect.asia/researchproject/networking/netbird/-/blob/master/Netbird%20Server%20Installation%20and%20Configuration.md
- VM / Container - min RAM=500MB
- Outgoing HTTPs network
```
- Reference: https://docs.netbird.io/how-to/add-machines-to-your-network


## Step 1.0: Creating Setup keys
**Note:** - Use setup keys to run automated deployments and add machines to your network at scale

- Access to https://tunnel.cloud-connect.asia:443, from the menu select **Setup Keys**, and click **Add key**

<img src="https://code.cloud-connect.asia/researchproject/networking/netbird/uploads/c4ead45bef225073f3346b73e8da6fce/image.png" >


- Enter relevant info as per the following screenshot, and click **Create key**

<img src="https://code.cloud-connect.asia/researchproject/networking/netbird/uploads/a0b8dbbf5f821b338a864dd1ffae1fa6/image.png" width=400>

- Copy and store the key, click **Done**

<img src="https://code.cloud-connect.asia/researchproject/networking/netbird/uploads/adc5863836ca576c62a47d756b81a071/image.png" width=400>

## Step 2.0: Hosts file configuration

- Access to VM client via SSH, for Linux, change the hosts file
```
sudo nano /etc/hosts
```
- Commented the following entry and save the hosts file
```
#127.0.1.1 secure-tunnel-server secure-tunnel-server
127.0.0.1 localhost
```

## Step 3.0: Adding Machines to Network
Reference: https://docs.netbird.io/how-to/add-machines-to-your-network

- Access to https://tunnel.cloud-connect.asia:443, from the menu select **Peers**, and click **Add peers**

<img src="https://code.cloud-connect.asia/researchproject/networking/netbird/uploads/efd86af36948750792a3faccf7fffb8e/image.png" >

- Select **Linux**

<img src="https://code.cloud-connect.asia/researchproject/networking/netbird/uploads/5a86039820e048acc001fabb28143c49/image.png" width=700>

- Access to VM client via SSH, for Linux, run the following command

```
curl -fsSL https://pkgs.netbird.io/install.sh | sh
```
- Run the following command to register to self-hosted Netbird server.

**Note:** get the setup-key from [Step 1](https://code.cloud-connect.asia/researchproject/networking/netbird/-/edit/master/Adding%20Machines%20to%20Network.md#step-10-creating-setup-keys)
```
netbird up --management-url https://tunnel.cloud-connect.asia:443 --setup-key A91349BF-EEAC-4DE4-84EA-A2E569579AE5
```

