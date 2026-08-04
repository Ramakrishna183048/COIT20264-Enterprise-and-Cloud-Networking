# week02
## Azure Virtual Machine and Cloud Shell

## Overview

This week focused on creating and managing an Azure Virtual Machine using the Microsoft Azure Portal and Azure Cloud Shell. The practical activities included deploying a virtual machine, configuring it through the Bash Cloud Shell, installing a web server, and understanding the concept and functions of virtual machines.

## Portfolio Tasks

## Task 1 – Build an Azure Virtual Machine (GUI Method)


### Objective
To create a Microsoft Azure Virtual Machine using the Azure Portal graphical user interface (GUI).

### Description
In this task, I successfully created a Virtual Machine using the Microsoft Azure Portal. I configured the required resource group, virtual machine settings, and deployment options by following the provided Microsoft Learn lab instructions. After the deployment was completed, I verified that the virtual machine was successfully created and recorded the required information.

### Virtual Machine Details

### Virtual Machine Details

- **Subscription:** Azure for Students
- **Resource Group:** IntroAzureRG
- **Virtual Machine Name:** my-vm
- **Operating System:** Ubuntu Server 24.04 LTS
- **VM Architecture:** x64
- **Region:** Australia East
- **Virtual Machine Size:** Standard D2s v3 (2 vCPUs, 8 GiB Memory)
- **Authentication Type:** Password
- **Username:** azureuser
- **Public IP Address:** 20.5.178.229
- **Private IP Address:** 10.0.0.4
- **Virtual Network:** my-vm-vnet

### Skills Demonstrated

- Microsoft Azure Portal
- Resource Group Creation
- Virtual Machine Deployment
- Azure Resource Management
- Cloud Infrastructure (IaaS)

### Screenshots

![Azure Virtual Machine](images/week2-task1-Microsoft.png)

### Outcome

Successfully created and deployed an Azure Virtual Machine using the Azure Portal and verified its deployment by recording the virtual machine details, including the public IP address and subscription information.


## Task 2 – Create a Virtual Machine

### Objective
To create a Microsoft Azure Virtual Machine using the Azure Portal.

### Description
I successfully created an Azure Virtual Machine using the Microsoft Azure Portal. The virtual machine was deployed within the **IntroAzureRG** resource group by following the Microsoft Learn tutorial. After deployment, I verified that the VM was created successfully and recorded its configuration details.

### Virtual Machine Details

- **Virtual Machine Name:** my-vm
- **Resource Group:** IntroAzureRG
- **Operating System:** Ubuntu Server 24.04 LTS
- **VM Architecture:** x64
- **VM Size:** Standard D2s v3
- **Public IP Address:** 20.5.178.229
- **Agent Status:** Ready

### Screenshot

![Azure Virtual Machine Overview](images/week2-task2-creat-virtual.png)
![Azure Virtual Machine Overview](images/week2-task2-myvm.png)

In this task, I used Azure Cloud Shell (Bash) to configure the virtual machine that I created in Task 1. I installed an Nginx web server using Azure CLI commands, checked the VM's public IP address, and confirmed that the web server was working by opening it in a web browser.

---

### Open Azure Cloud Shell

First, I logged into the Azure Portal and opened **Cloud Shell**. I selected the **Bash** environment to run the Azure CLI commands.

### Install Nginx

Next, I ran the following Azure CLI command to install the Nginx web server on my virtual machine.

```bash
az vm extension set \
  --resource-group "IntroAzureRG" \
  --vm-name my-vm \
  --name customScript \
  --publisher Microsoft.Azure.Extensions \
  --version 2.1 \
  --settings '{"fileUris":["https://raw.githubusercontent.com/MicrosoftDocs/mslearn-welcome-to-azure/master/configure-nginx.sh"]}' \
  --protected-settings '{"commandToExecute":"./configure-nginx.sh"}'
```

The command ran successfully, and the provisioning state showed **Succeeded**, which confirmed that Nginx had been installed correctly.

![Nginx installation](images/week2-task2-cli-success.png)

### Step 3: Retrieve the Public IP Address

After installing Nginx, I used the following command to find the public IP address of my virtual machine.

```bash
az vm show \
  --resource-group IntroAzureRG \
  --name my-vm \
  --show-details \
  --query publicIps \
  --output tsv
```

**Output**
![Public IP Address](images/week2-task2-sucessful.png)

```text
20.5.178.229
```
---

## Step 4: Verify the Web Server

Finally, I copied the public IP address and opened it in my web browser.

```text
http://20.5.178.229
```

The browser displayed the following message:

> **Welcome to Azure! My name is my-vm.**

This confirmed that the Nginx web server was installed successfully and was running on my Azure virtual machine.

![Webpage AZURE my-vm](images/week2-task3-webpage.png)

---

## Result

In this task, I successfully configured my Azure virtual machine using Azure Cloud Shell. I installed the Nginx web server with Azure CLI, retrieved the VM's public IP address, and verified that the web server was working by opening it in a web browser.

---

### Outcome
Successfully deployed and verified an Azure Virtual Machine using the Microsoft Azure Portal.
