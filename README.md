<img src="https://www.starwindsoftware.com/blog/wp-content/uploads/2019/03/racsultat-de-recherche-dimages-pour-azure-vm.png" width="100%">

# Learn How to Create a Virtual Machine in Azure

This guide outlines a step-by-step approach to setting up Windows and Linux virtual machines (VMs) in Microsoft Azure. 

## 🚨 Prerequisites

- [Setting up an active Azure account](https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account/)

## Technologies Used

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
After logging into your Azure account, you’ll be taken to the Quickstart Center within the Azure Portal.

### Locate Resource Groups
Use the search bar at the top of the Azure Portal. Type "resource" and choose **Resource Groups** from the list of suggested results.

<img width="1507" alt="Screenshot 2025-06-03 at 9 49 55 AM" src="https://github.com/user-attachments/assets/d97ff385-f7bd-4d72-9aee-552339452c72" />

### Initiate Resource Group Creation
Click the **+ Create** button to add a new one.

<img width="1507" alt="Screenshot 2025-06-03 at 9 50 26 AM" src="https://github.com/user-attachments/assets/5e4ee057-4382-4241-a9a1-13f354aa3363" />

### Configure Resource Group Settings

<img width="1507" alt="Screenshot 2025-06-03 at 9 52 29 AM" src="https://github.com/user-attachments/assets/16795ebe-afa0-4e61-b847-874a165a6e30" />


- **Subscription**: Make sure that the appropriate subscription is selected from the dropdown menu.
- **Name**: Give the Resource Group a clear, descriptive name (e.g., "github-rg"). This group will act as the container for your virtual machines.
- **Region**: Select a region **I used (US) East US 2**. 

Go ahead and press** Next** until you reach the **Review + Create** section.

### Finalize Creation
Confirm the Resource Group details, including name and region, and select **Create**. Upon completion, you will be redirected to the Resource Groups section, where the new group will be visible.

---

## Step 2: Set Up a Windows VM

### Navigate to Virtual Machines
In the Azure Portal, use the search bar to enter "virtual" and select **Virtual Machines** from the results.

<img width="1507" alt="Screenshot 2025-06-03 at 9 55 16 AM" src="https://github.com/user-attachments/assets/59db1706-4e03-45a3-a0d1-357a472e4a91" />

### Begin VM Creation
Select the **+ Create** button to start the process.

<img width="1507" alt="Screenshot 2025-06-03 at 9 55 41 AM" src="https://github.com/user-attachments/assets/f15b777a-6a81-4a6f-bf56-8ff2ca88140d" />

### Specify VM Type
From the dropdown menu, select **Azure virtual machine**, then click **Create**.


### Set Up Core Settings

<img width="1507" alt="Screenshot 2025-06-03 at 9 56 34 AM" src="https://github.com/user-attachments/assets/de113efb-89d0-4e1b-a86d-a4ebd6b6902d" />

- **Subscription**: Make sure the correct subscription is selected
- **Resource Group**: Choose the Resource Group created earlier (e.g., "github-rg")
- **VM Name**: Enter "windows-vm"
- **Region**: Select **(US) East US 2** to align with the Resource Group (Select the same region that you selected in your resource group!)
- **Image**: Select **Windows 10 Pro, version 22H2** as the operating system )

### Select VM Size

![VM Size Selection](https://github.com/user-attachments/assets/0508247f-af54-4652-8298-5718952d2d57)

In the **Size** field, choose **Standard_D2s_v3 - 2 vCPUs, 8 GiB memory**. If unavailable, select **See all sizes** and choose an equivalent with at least 2 vCPUs and 8 GiB memory.

### Define Administrative Credentials

<img width="1440" alt="Screenshot 2025-06-03 at 9 58 02 AM" src="https://github.com/user-attachments/assets/fd10262d-7b54-4bfe-86b2-47c06c210e47" />

* Set up a username and password for the virtual machine. Keep a note of this, as they will be needed for Remote Desktop Protocol (RDP) access.
* In the **Licensing** section, check the box to confirm that you're eligible for Windows 10—this is mandatory in order to deploy the virtual machine. 


### Configure Disks
Click **Next: Disks** and keep the default disk settings unchanged.

<img width="859" alt="Screenshot 2025-06-03 at 9 58 32 AM" src="https://github.com/user-attachments/assets/55e54485-6374-40fe-a832-02fde9e5a1bf" />

### Configure Networking

<img width="1440" alt="Screenshot 2025-06-03 at 10 01 09 AM" src="https://github.com/user-attachments/assets/0e3fcf67-5be4-470c-bbec-851355ec7963" />

- Set up a new Virtual Network (e.g., "github-vnet") and make sure to note this name for later use.
-  Keep the rest of the default settings unchanged.
- Click the **Review + Create** button at the bottom of the screen.


### Validate and Deploy

<img width="1440" alt="Screenshot 2025-06-03 at 10 02 10 AM" src="https://github.com/user-attachments/assets/8f9d1f08-ecaa-4772-9477-a11f5ec6d66f" />

Review all settings, such as subscription, Resource Group, region, VM name, image, size, and RDP configuration. Then, click **Create** to proceed.

### Monitor Deployment

<img width="1440" alt="Screenshot 2025-06-03 at 10 06 51 AM" src="https://github.com/user-attachments/assets/0ebcc90b-2ee7-4aac-8593-c620c8559ca8" />

Deployment may take up to several minutes. When completed, the message "Your deployment is complete" will appear. Select **Create another VM** to proceed with the Linux VM.

---

## Step 3: Set Up a Linux VM

### Begin Linux VM Configuration

<img width="1440" alt="Screenshot 2025-06-03 at 10 08 35 AM" src="https://github.com/user-attachments/assets/1b7c13ba-fda9-4ecc-a246-9e03a75893f5" />

On the VM creation page, set up the following:
- **Resource Group**: Select the same Resource Group (e.g., "github-rg")
- **Name**: Enter "linux-vm"
- **Region**: Set to same region as before 
- **Image**: Choose **Ubuntu Server 22.04 LTS**

### Define VM Size and Authentication Details

<img width="1440" alt="Screenshot 2025-06-03 at 10 09 00 AM" src="https://github.com/user-attachments/assets/d30d2b95-5718-46be-9751-c6d017757b67" />
<img width="1440" alt="Screenshot 2025-06-03 at 10 10 30 AM" src="https://github.com/user-attachments/assets/5b5aa1e3-829b-4a71-9bab-264d9cae97dd" />


- **Size**: Select **Standard_D2s_v5 - 2 vCPUs, 8 GiB memory**, same as the Windows VM
- **Authentication type**: Set to **Password** (selected default is SSH public key, so need to click password)
- **Credentials**: Enter a username and password. You can reuse the Windows VM credentials you used before for your convenience. 

Select **Next** to proceed to disks and maintain the default settings. Proceed again by pressing **Next** to networking.

### Configure Networking

<img width="1440" alt="Screenshot 2025-06-03 at 10 10 59 AM" src="https://github.com/user-attachments/assets/b5dabd3d-3c98-4ea0-bdb1-7ce934d137fc" />

- **Virtual Network**: Choose the Virtual Network that was created  for the Windows VM (e.g., "github-vnet")
- Keep the the rest of the default settings in Networking
- Continue **Next** until you reach the **Review + Create** page

### Validate and Deploy

<img width="1440" alt="Screenshot 2025-06-03 at 10 13 49 AM" src="https://github.com/user-attachments/assets/f8b7549e-8732-4101-9865-d1e2143923b2" />

Ensure the settings are what you want. Once done, select **Create**.

### Monitor Deployment and Review VMs


The deployment will take several minutes. Upon completion, the message "Your deployment is complete" will appear.

Use the search bar near the top of the page to return to **Virtual Machines**. "Windows-VM" and "Linux-VM" will both be listed, showing information such as resource group, region, size, operating system, and public IP addresses.

**Note**: In the Virtual Machines (VM) section, you can use the Start, Stop, and Restart options to control the state of your VMs. To save costs, be sure to stop VMs when they’re not being used. For extra practice, you can delete the Resource Group and go through the setup process again.
To stop a VM, click the checkbox by the name of the VM, click the three dots next to open query and select stop. It will ask again if you want to stop the VM, just simply click yes. 

<br/><br/>


<br/>


## Conclusion

This process effectively sets up a Resource Group along with two virtual machines in Microsoft Azure: one running Windows 10 Pro and the other using Ubuntu Server 22.04 LTS. By leveraging these cloud-based environments, you gain flexible, on-demand computing power without relying on traditional physical servers, making IT operations more scalable and budget-friendly.



This concludes the deployment process! Congrats on setting up a resource group and two VM's in Azure!

---

<div align="center">

<a href="HTTP://www.github.com/jadenhinds-hub">- BACK TO MAIN PAGE -</a>

</div>
