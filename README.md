![Screenshot 2024-06-08 160457](https://github.com/lucky-the-racer/assignment3/assets/114669843/b0e8122a-b05c-4fb1-8d5c-749cfa216feb)
![Screenshot 2024-06-08 160407](https://github.com/lucky-the-racer/assignment3/assets/114669843/6d205d15-2b69-496d-b6ec-74ee4eb1a0eb)
![Screenshot 2024-06-08 160540](https://github.com/lucky-the-racer/assignment3/assets/114669843/45ba1fe3-3043-4546-993d-fad1a3f2099f)
![Screenshot 2024-06-08 160636](https://github.com/lucky-the-racer/assignment3/assets/114669843/7ee83b76-9b7d-4ea9-9777-bdff4d1569ef)

# Azure Infrastructure Setup

## 1. Deploy Linux and Windows Virtual Machine (VM) and Access Them
### Steps:
1. **Create a Linux VM:**
    - Go to the Azure portal and click on "Create a resource."
    - Select "Virtual Machine."
    - Choose "Ubuntu Server" for the image.
    - Fill in the required fields (VM name, region, size, etc.).
    - Under "Administrator account," choose "SSH public key."
    - Upload your SSH public key.
    - Click "Review + create," then "Create."

2. **Access the Linux VM using SSH:**
    - Open your terminal.
    - Use the command: `ssh username@your_vm_public_ip`

3. **Create a Windows VM:**
    - Go to the Azure portal and click on "Create a resource."
    - Select "Virtual Machine."
    - Choose "Windows Server" for the image.
    - Fill in the required fields (VM name, region, size, etc.).
    - Under "Administrator account," set a username and password.
    - Click "Review + create," then "Create."

4. **Access the Windows VM using RDP:**
    - Download an RDP file from the Azure portal.
    - Open the RDP file and connect using the username and password you set.
## 2. Create an App Service Plan and Provision a Web App
### Steps:
1. **Create an App Service Plan:**
    - Go to the Azure portal and click on "Create a resource."
    - Search for "App Service Plan" and select it.
    - Fill in the required fields (name, resource group, region, pricing tier).
    - Click "Review + create," then "Create."

2. **Provision a Web App:**
    - Go to the Azure portal and click on "Create a resource."
    - Search for "Web App" and select it.
    - Fill in the required fields (name, publish, runtime stack, etc.).
    - Choose the App Service Plan you created.
    - Click "Review + create," then "Create."

3. **Deploy a Simple Welcome Page:**
    - Use the Azure portal's built-in editor to create a simple HTML file.
    - Or, deploy your code using GitHub, FTP, or other deployment methods
## 3. Create Azure Container Registry (ACR) and Pull Image from ACR
### Steps:
1. **Create ACR:**
    - Go to the Azure portal and click on "Create a resource."
    - Search for "Container Registry" and select it.
    - Fill in the required fields (registry name, resource group, location).
    - Click "Review + create," then "Create."

2. **Push an Image to ACR:**
    - Tag your Docker image: `docker tag myimage acrname.azurecr.io/myimage:tag`
    - Login to ACR: `az acr login --name acrname`
    - Push the image: `docker push acrname.azurecr.io/myimage:tag`

3. **Pull the Image from ACR:**
    - Login to ACR from your machine: `docker login acrname.azurecr.io`
    - Pull the image: `docker pull acrname.azurecr.io/myimage:tag`
## 4. Create Container Instance and Deploy a Docker Application
### Steps:
1. **Create a Container Instance:**
    - Go to the Azure portal and click on "Create a resource."
    - Search for "Container Instances" and select it.
    - Fill in the required fields (name, resource group, container image, etc.).
    - Click "Review + create," then "Create."

2. **Deploy a Simple Docker Application:**
    - Use a public Docker image or your image from ACR.
    - Specify the image and settings during the creation of the container instance.

3. **Create Container Groups:**
    - Container groups can be created by defining multiple containers in the same instance during the creation process.
    - Ensure they share the same network and storage resources.

4. **Test Functionality:**
    - Access the container instance using its FQDN or IP address.
    - Ensure the application is running as expected.
         
