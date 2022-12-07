## How to create windows virtual machine in Azure platform ##



Azure virtual machine (VM) is a computing service that allows to host or access applications virtually in the cloud and it provides the functionality just like a physical computer. This guideline shows how to deploy and install VM using Azure platform

, how to deploy a simple virtual machine, open a network port for web traffic, and install a basic web server.



create a free account if you haven't purchased azure subscription.



## Sign into Azure ##

Sign into the Azure portal at https://portal.azure.com.

## create virtual machine ##

1. Enter virtual machines in the search.



2. Under Services, select Virtual machines.



3. In the Virtual machines page, select Create and then Azure virtual machine. The Create a virtual machine page opens.



4. Under Instance details, enter my VM for the Virtual machine name and choose Windows Server 2019 Datacenter

<img width="587" alt="instance-details" src="https://user-images.githubusercontent.com/102283999/204968569-bcab18b2-468a-4d57-9bf0-bc807d2cbf92.png">

5. Under **Administrator account** , provide a username, such as *azureuser* and a *password* . The password must be at least 12 characters long and meet the defined complexity requirements.

<img width="590" alt="administrator-account" src="https://user-images.githubusercontent.com/102283999/204969198-038669e3-523a-472f-8c82-737fc8fecae2.png">

6. Under **Inbound port rules** , choose Allow selected ports and then select **RDP (3389)** and **HTTP (80)** from the drop-down.

 <img width="586" alt="inbound-port-rules" src="https://user-images.githubusercontent.com/102283999/204969278-dcb38cc6-a17d-400b-8eeb-30a4577af22a.png">

7. Leave the remaining defaults and then select the **Review + create** at the bottom of the page.

<img width="417" alt="lic" src="https://user-images.githubusercontent.com/102283999/204970323-40e337bf-94cd-4bb6-a030-b15e63930061.png">

8. After validation runs, select the  **create** button at the bottom of the page.

<img width="386" alt="image" src="https://user-images.githubusercontent.com/102283999/204970454-6b3ed399-7447-4578-a3fb-35348a07a1f2.png">

9. After deployment is complete, select Go to **resource** .

<img width="412" alt="image" src="https://user-images.githubusercontent.com/102283999/204970533-c517408a-035f-487b-88af-298c108bacae.png">

## Connect to virtual machine ##

Create a remote desktop connection to the virtual machine. These directions tell you how to connect to your VM from a Windows computer. On a Mac, you need an RDP client such as this Remote Desktop Client from the Mac App Store.



1. On the overview page for your virtual machine, select the ***Connect > RDP***.

 <img width="419" alt="image" src="https://user-images.githubusercontent.com/102283999/204970985-ff3dd6e3-9f82-4c2d-b1fc-b016446052c5.png">

2. In the ***Connect with RDP tab***, keep the default options to connect by IP address, over port 3389, and click ***Download RDP file***.

<img width="420" alt="image" src="https://user-images.githubusercontent.com/102283999/204971056-ee6bed5f-3c98-4e7d-ab13-6fb8c81ab649.png">

3. Open the downloaded RDP file and click **connect** when prompted.

4.In the Windows Security window, select ***More choices*** and then Use a ***different account***. Type the username as **localhost\username** , enter the password you created for the virtual machine, and then click **OK**.

5.You may receive a certificate warning during the sign-in process. Click **Yes** or **Continue** to create the connection.



# Install Web server #

To see your VM in action, install the IIS web server. Open a PowerShell prompt on the VM and run the following command:

```

Install-WindowsFeature -name <mark>Web-Server -IncludeManagementTools

```

When done, close the RDP connection to the VM.



# View the IIS Welcome page #

In the portal, select the VM and in the overview of the VM, hover over the IP address to show **Copy to clipboard**. Copy the IP address and paste it into a browser tab. The default IIS welcome page will open, and should look like this:

<img width="422" alt="image" src="https://user-images.githubusercontent.com/102283999/204980392-68567695-184b-4213-975e-7b540c7af2ed.png">

# clean up Resources #

When no longer needed, you can delete the **resource** group, virtual machine, and all related resources.



1. On the Overview page for the VM, select the Resource group link.

2. At the top of the page for the resource group, select **Delete resource group** .

3. A page will open warning you that you are about to **Delete resources**. Type the name of the resource group and select **Delete** to finish deleting the resources and the resource group.

Next: [Virtual Machine List](https://github.com/Merlin-Melody/techwritr22/blob/main/virtual%20machine%20list%20API%20doc.md)


