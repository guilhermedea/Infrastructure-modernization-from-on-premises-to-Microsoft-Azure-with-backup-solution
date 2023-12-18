# Infrastructure modernization, from on-premises to Microsoft Azure with backup solution using Azure Files, Azure Backup and Recovery Services Vault.

![picture with the words Cloud Project and icons of the services used](https://miro.medium.com/v2/resize:fit:720/format:webp/0*f_ElIctPvywuoBMh.jpg)

In this project based on a real-world scenario, I acted as a Cloud Specialist to modernize and migrate an on-premises infrastructure environment to 
Microsoft Azure. I deployed a set of Virtual Machines, the infrastructure, a shared file system and replaced backups from tape to cloud backups with
99.9% (3-nines) availability.

I used a Resource Group to organize resources, a VNet with a subnet where we would have the provisioning of 2 Application VMs and Azure Files as a 
shared file system solution between our Application VMs.

All the power and reliability of Azure Backup with Azure Recovery Services have been used to configure the backup of files in the shared file system. 
Once again, Azure Backup has been used to move the files to the Recovery Services Vault.

![picture showing a graph of the solution architecture](https://miro.medium.com/v2/resize:fit:720/format:webp/0*k8GtSm__-mO4G8WY.jpg)

The whole process was very quick, and could be easily escalated to meet many different demands. I began provisioning two virtual machines in a previously created
VNet. While the two machines were finishing their deployment, I created a Storage Account, which centralizes the various kind of storage available on Azure. In
this account I created a Azure Files, which is the shared filed system and easily configurable. Using a script given by Azure after creating the Azure Files,
I logged on the machines using SSH and ran the command, mounting the Azure Files on both machines. I did a quick test creating 5 simple files on the first machine,
which instantly appeared on the second.

On Azure dashboard, I created a backup vault for the shared file system, with a daily backup policy. I ran the initial backup, which took less than a minute. 
On the first VM I listed the files and them removed two of them. Back to Azure dashboard, I activated the File Recovery System, restoring the files,
which appeared back on the machines again.

![picture showing terminal listing files](https://miro.medium.com/v2/resize:fit:720/format:webp/0*aIFfK_Oy62GSEZiM.png)

Azure Files is a very powerful system, giving lots of control over it’s configurations, like storage limits and performance options. 
But more importantly, Azure Files is quickly escalable, allowing a company to quickly answer to demand spikes. Currently migrating infrastructures have a
lot to gain with this process, gaining much more agility and security that a on-premises option could ever giver.



