# SOC-Secure-Network-Configuration-with-Azure-Private-Link-Firewall-and-NC-7-Compliance-Lab
<p align="center">

![Screenshot 2024-10-20 194424](https://github.com/user-attachments/assets/1eba913a-92dc-4e3b-a0ec-9fa711b708f5)

</p>

In this lab, I configured secure network boundaries for Azure resources following NIST 800-53 NC-7 guidelines. Using Azure Private Link and firewall settings, I restricted public access to Azure Key Vault and Storage Account instances, ensuring they are accessible only through private virtual networks (VNets). I verified the correct setup by observing private IP addresses and inspecting the Network Watcher topology. This lab demonstrates my ability to enhance network security by implementing private endpoints, firewalls, and monitoring tools in alignment with NC-7 boundary protection standards.




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Key Vaults
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1 - Configure Azure Private Link and Firewall for your Azure Key Vault instance
- Step 2 - Configure Azure Private Link and Firewall for your Azure Storage Account instance
- Step 3 - Observe Network Watcher Topology for the region and resource group all of your stuff is in.
- Step 4 - Login to “windows-vm” and check the IP addresses of your Key Vault and Storage Account instances.

<h2>Deployment and Configuration Steps</h2>

-  Step 1 - Configure Azure Private Link and Firewall for your Azure Key Vault instance
- Ensure you use the same region and VNet the rest of your VMs are in
   ![Screenshot 2024-10-20 195409](https://github.com/user-attachments/assets/cdd5db33-a42f-46d9-b11a-918b93c94b4e)
   ![Screenshot 2024-10-20 200011](https://github.com/user-attachments/assets/0bfa07c9-72dd-4e5a-a687-b1f8026bf72d)
	
- Step 2 - Configure Azure Private Link and Firewall for your Azure Storage Account instance
- Disable Public Access (you can only access from within your VMs now.)
- This is done on the network tab as well as the Settings -> configuration “Allow Blob public access → Disabled” as well
  ![Screenshot 2024-10-20 200656](https://github.com/user-attachments/assets/39f26c1b-9028-442d-917c-b611407eb4e0)
  ![Screenshot 2024-10-20 200827](https://github.com/user-attachments/assets/8bbaaaa5-0e84-42ca-917c-293fc3ee7fdc)
  ![Screenshot 2024-10-20 201030](https://github.com/user-attachments/assets/f89c2e74-3896-48b9-83b5-aee8223283f8)


- Step 3 - Observe Network Watcher Topology for the region and resource group all of your stuff is in.
- Observe the Key Vault and Storage Account Private Endpoints are there
  ![Screenshot 2024-10-20 201908](https://github.com/user-attachments/assets/0f5ef743-ac24-4d6b-a0ed-37c9fc689279)
  ![Screenshot 2024-10-20 202212](https://github.com/user-attachments/assets/4cb136e6-1c7e-4ddc-baf4-e398ad23332f)
  ![Screenshot 2024-10-20 202309](https://github.com/user-attachments/assets/d36d4d7a-cfb6-4eb0-8f75-a5a79b4692d9)

- Step 4 - Login to “windows-vm” and check the IP addresses of your Key Vault and Storage Account instances.
- They should be private addresses, indicating the resources have been probably integrated into private VNet:
  ![Screenshot 2024-10-20 202920](https://github.com/user-attachments/assets/2e92c38b-daa7-4c12-a58f-0e4f128722d7)

- After running the nslookup command, the ip address came back as 10.0.0.6 which means our private endpoint is working.
  ![Screenshot 2024-10-20 204050](https://github.com/user-attachments/assets/8effcfa4-6013-402e-ad7c-5a46c3c73e00)

- Done the same for our storage account which came back as a private address which confirms our private endpoint is working as well.
  ![Screenshot 2024-10-20 204632](https://github.com/user-attachments/assets/de11c36f-2719-4759-8841-928fb03bf8cf)









