<img src="https://www.starwindsoftware.com/blog/wp-content/uploads/2019/03/racsultat-de-recherche-dimages-pour-azure-vm.png" width="100%">

# Learn How to Create a Virtual Machine in Azure

This guide outlines a step-by-step approach to setting up Windows and Linux virtual machines (VMs) in Microsoft Azure. 

## 🚨 Prerequisites

- [Setting up an active Azure account](https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account/)

## Technologies Utilized

- Microsoft Azure (Virtual Machines)

## Operating Systems

- macOS Sequoia
- Windows 10 Pro (22H2)
- Ubuntu Server 22.04 LTS

## Procedure Overview

Step 1: Set up a Resource Group in Azure
Step 2: Deploy a Windows Virtual Machine in Azure
Step 3: Deploy a Linux Virtual Machine in Azure


---

## Step 1: Setting Up a Resource Group in Azure

### Access the Azure Portal
Upon signing into your Azure account, you will be directed to the Azure Portal's Quickstart Center.

### Locate Resource Groups
Utilize the search bar at the top of the portal. Enter "resource" and select **Resource Groups** from the suggested options.

<img width="1507" alt="Screenshot 2025-06-03 at 9 49 55 AM" src="https://github.com/user-attachments/assets/d97ff385-f7bd-4d72-9aee-552339452c72" />

### Initiate Resource Group Creation
If no resource groups are listed, select the **+ Create** button.

<img width="1507" alt="Screenshot 2025-06-03 at 9 50 26 AM" src="https://github.com/user-attachments/assets/5e4ee057-4382-4241-a9a1-13f354aa3363" />

### Configure Resource Group Settings

<img width="1507" alt="Screenshot 2025-06-03 at 9 52 29 AM" src="https://github.com/user-attachments/assets/16795ebe-afa0-4e61-b847-874a165a6e30" />


- **Subscription**: Verify that the appropriate subscription is selected from the dropdown menu
- **Name**: Assign a descriptive name to the Resource Group (e.g., "CloudInfraRG"). This will serve as the container for your VMs
- **Region**: Select **(US) East US 2**. Consistency in region selection across resources is critical to prevent configuration conflicts

Proceed by pressing **Next** until you reach the **Review + Create** section.

### Finalize Creation
Confirm the Resource Group details, including name and region, and select **Create**. Upon completion, you will be redirected to the Resource Groups section, where the new group will be visible.

---

## Step 2: Provision a Windows VM

### Navigate to Virtual Machines
In the Azure Portal, use the search bar to enter "virtual" and select **Virtual Machines** from the results.

<img width="1507" alt="Screenshot 2025-06-03 at 9 55 16 AM" src="https://github.com/user-attachments/assets/59db1706-4e03-45a3-a0d1-357a472e4a91" />

### Begin VM Creation
Select the **+ Create** button to initiate the process.

<img width="1507" alt="Screenshot 2025-06-03 at 9 55 41 AM" src="https://github.com/user-attachments/assets/f15b777a-6a81-4a6f-bf56-8ff2ca88140d" />

### Specify VM Type
Choose **Azure virtual machine** from the dropdown and select **Create**.

![VM Type Selection](https://github.com/user-attachments/assets/2e804b31-bfbb-4097-8302-2593baa666f7)

### Configure Core Settings

<img width="1507" alt="Screenshot 2025-06-03 at 9 56 34 AM" src="https://github.com/user-attachments/assets/de113efb-89d0-4e1b-a86d-a4ebd6b6902d" />

- **Subscription**: Ensure the correct subscription is selected
- **Resource Group**: Choose the Resource Group created earlier (e.g., "CloudInfraRG")
- **VM Name**: Enter "windows-vm"
- **Region**: Select **(US) East US 2** to align with the Resource Group
- **Image**: Select **Windows 10 Pro, version 22H2** as the operating system (avoid selecting Windows Server images)

### Select VM Size

![VM Size Selection](https://github.com/user-attachments/assets/0508247f-af54-4652-8298-5718952d2d57)

In the **Size** field, choose **Standard_D2s_v3 - 2 vCPUs, 8 GiB memory**. If unavailable, select **See all sizes** and choose an equivalent with at least 2 vCPUs and 8 GiB memory.

### Define Administrative Credentials

<img width="1440" alt="Screenshot 2025-06-03 at 9 58 02 AM" src="https://github.com/user-attachments/assets/fd10262d-7b54-4bfe-86b2-47c06c210e47" />

- Create a username and password for the VM. Store these credentials securely, as they are required for Remote Desktop Protocol (RDP) access
- Under **Licensing**, check the box to confirm eligibility for Windows 10. This is mandatory for successful deployment

### Configure Disks
Select **Next: Disks** and retain the default disk configurations.

<img width="859" alt="Screenshot 2025-06-03 at 9 58 32 AM" src="https://github.com/user-attachments/assets/55e54485-6374-40fe-a832-02fde9e5a1bf" />

### Configure Networking

<img width="1440" alt="Screenshot 2025-06-03 at 10 01 09 AM" src="https://github.com/user-attachments/assets/0e3fcf67-5be4-470c-bbec-851355ec7963" />

- Create a new Virtual Network (e.g., "cloud-vnet"). Record this name for future reference
- Retain default settings for Subnet, Public IP, and the RDP port (3389) to enable remote access
- Continue **Next** until you reach the **Review + Create** page

### Validate and Deploy

<img width="1440" alt="Screenshot 2025-06-03 at 10 02 10 AM" src="https://github.com/user-attachments/assets/8f9d1f08-ecaa-4772-9477-a11f5ec6d66f" />

Verify the configuration, including subscription, Resource Group, region, VM name, image, size, and RDP settings. Select **Create**.

### Monitor Deployment

<img width="1440" alt="Screenshot 2025-06-03 at 10 06 51 AM" src="https://github.com/user-attachments/assets/0ebcc90b-2ee7-4aac-8593-c620c8559ca8" />

Deployment may take several minutes. Upon completion, the message "Your deployment is complete" will appear. Select **Create another VM** to proceed with the Linux VM.

---

## Step 3: Provision a Linux VM

### Initiate Linux VM Setup

<img width="1440" alt="Screenshot 2025-06-03 at 10 08 35 AM" src="https://github.com/user-attachments/assets/1b7c13ba-fda9-4ecc-a246-9e03a75893f5" />

From the VM creation screen, configure the following:
- **Resource Group**: Select the same Resource Group (e.g., "CloudInfraRG")
- **Name**: Enter "linux-vm"
- **Region**: Set to **(US) East US 2** for consistency
- **Image**: Choose **Ubuntu Server 22.04 LTS**

### Specify Size and Authentication

<img width="1440" alt="Screenshot 2025-06-03 at 10 09 00 AM" src="https://github.com/user-attachments/assets/d30d2b95-5718-46be-9751-c6d017757b67" />
<img width="1440" alt="Screenshot 2025-06-03 at 10 10 30 AM" src="https://github.com/user-attachments/assets/5b5aa1e3-829b-4a71-9bab-264d9cae97dd" />


- **Size**: Select **Standard_D2s_v5 - 2 vCPUs, 8 GiB memory**, consistent with the Windows VM
- **Authentication type**: Set to **Password** (default is SSH public key)
- **Credentials**: Provide a username and password. For simplicity, you may reuse the Windows VM credentials. Store these securely

Select **Next** to proceed to disks and maintain the default settings. Proceed again by pressing **Next** to networking.

### Configure Networking

<img width="1440" alt="Screenshot 2025-06-03 at 10 10 59 AM" src="https://github.com/user-attachments/assets/b5dabd3d-3c98-4ea0-bdb1-7ce934d137fc" />

- **Virtual Network**: Choose the Virtual Network created for the Windows VM (e.g., "cloud-vnet")
- Retain default settings for Subnet and Public IP
- Continue **Next** until you reach the **Review + Create** page

### Validate and Deploy

<img width="1440" alt="Screenshot 2025-06-03 at 10 13 49 AM" src="https://github.com/user-attachments/assets/f8b7549e-8732-4101-9865-d1e2143923b2" />

Confirm the settings, including Resource Group, region, VM name, image, size, and network configuration. Select **Create**.

### Monitor Deployment and Review VMs


The deployment will take several minutes. Upon completion, the message "Your deployment is complete" will appear.

Use the search bar to return to **Virtual Machines**. Both "Windows-VM" and "Linux-VM" will be listed, displaying details such as resource group, region, operating system, and public IP addresses.

**Note**: The Start, Stop, and Restart options in the Virtual Machines section allow you to manage VM states. To optimize costs, stop VMs when not in use. For additional practice, you may delete the Resource Group and repeat the process.
<br/><br/>

<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

<br/>

<div align="center"> <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExazdxOXFrZDl6YmUwdGgxamhpYzRuNWFpbnV5bWRyc2lsYXlsZHNzMiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/l1AsI389lnxkvQHAc/giphy.gif" width="100%"> </div>

<br/>

<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

## Conclusion

This procedure successfully establishes a Resource Group, a Windows VM running Windows 10 Pro, and a Linux VM running Ubuntu Server 22.04 LTS in Microsoft Azure. These virtualized environments provide scalable, cost-efficient resources for IT operations, eliminating the need for physical hardware. 

Enterprises leverage such cloud solutions for their flexibility and economic benefits. Ensure VMs are stopped when idle to manage subscription costs.

**Key takeaways:**
- Both VMs are deployed in the same region and virtual network for optimal connectivity
- Authentication credentials are required for accessing both Windows (RDP) and Linux (SSH) VMs
- Resource management is critical for cost optimization in cloud environments

This concludes the deployment process.

---

<div align="center">

<a href="HTTP://www.github.com/mxwllslvr">- BACK TO MAIN PAGE -</a>

</div>
