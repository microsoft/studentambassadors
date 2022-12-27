# Creating an Azure Virtual Machine And running a React App.
<p align="center"><img src=https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/n-tier/images/single-vm-diagram.png><br>Azure Virtual Machines</p>

Azure is a platform and architecture for cloud computing developed by
Microsoft for creating, delivering, and managing applications and
services through a worldwide network of data centers under Microsoft\'s
management. A web-based management and monitoring tool for Azure
resources, such as virtual machines, web apps, and storage accounts, is
called the Azure portal.

The Azure portal offers information on several solutions, including
Azure Virtual Machines (VMs). Azure VMs are virtualized environments
that run in the cloud and can be used to host programs and services.

Azure Virtual machines are software emulations of physical computers.

-   Include virtual machine's operating system, processor, memory (RAM),
    storage and networking among other hardware and software resources.

-   It is categorized as Infrastructure as a Service (IaaS) that provide
    total control and customization

## Creating Azure Virtual Machine Via Azure Portal

To create and use an Azure Virtual Machine (VM), you will need to
provision a VM in the Azure portal. Provisioning a VM involves
specifying the configuration options for the virtual machine, including
the operating system, size, and location.

> To provision an Azure virtual machine, follow these steps:

1.	Sign in to the Azure portal (https://portal.azure.com).
2.	Click the "Create a resource" button in the top left corner of the portal.
3.	In the "Search the Marketplace" field, search for "virtual machine".
4.	Click the "Virtual machine" option that appears in the search results.
5.	In the Virtual machines page, select Create and then Azure virtual machine. The Create a virtual machine page opens.
6. Under Project details :- Select your subscription to manage deployed resources and costs
7.	Under Instance details, enter myVM for the Virtual machine name and choose Windows Server 2019 Datacenter - Gen 2 for the Image. Leave the other defaults.
<p align="center"><img src=https://learn.microsoft.com/en-us/azure/virtual-machines/windows/media/quick-create-portal/instance-details.png><br>Instance details</p>
8.	Under Administrator account, provide a username, such as azureuser and a password. The password must be at least 12 characters long and meet the defined complexity requirements.
<p align="center"><img src=https://learn.microsoft.com/en-us/azure/virtual-machines/windows/media/quick-create-portal/administrator-account.png><br></p>
9.	Under Inbound port rules, choose Allow selected ports and then select RDP (3389) and HTTP (80) from the drop-down.
<p align="center"><img src=https://learn.microsoft.com/en-us/azure/virtual-machines/windows/media/quick-create-portal/inbound-port-rules.png><br></p>
10.	Leave the remaining defaults and then select the Review + create button at the bottom of the page.
<p align="center"><img src=https://learn.microsoft.com/en-us/azure/virtual-machines/windows/media/quick-create-portal/review-create.png><br></p>
11.	 After validation runs, select the Create button at the bottom of the page.
<p align="center"><img src=https://learn.microsoft.com/en-us/azure/virtual-machines/windows/media/quick-create-portal/validation.png><br></p>
12.	 After deployment is complete, select Go to resource.
<p align="center"><img src=https://learn.microsoft.com/en-us/azure/virtual-machines/windows/media/quick-create-portal/next-steps.png><br></p>


Under Instance details, enter myVM for the Virtual machine name and choose Windows Server 2019 Datacenter - Gen 2 for the Image. Leave the other defaults.
<p align="center"><img src=https://learn.microsoft.com/en-us/azure/virtual-machines/windows/media/quick-create-portal/validation.png><br></p>
Note : on step 6 Some users will now see the option to create VMs in multiple zones. To learn more about this new capability, [See Create virtual machines in an availability zone](https://learn.microsoft.com/en-us/azure/virtual-machines/create-portal-availability-zone).

It may take a few minutes for the virtual machine to be provisioned and
become available. Once the VM has been created, you can access it
through the Azure portal by clicking on its name in the list of virtual
machines. From the virtual machine page, you can start, stop, and
restart the VM, as well as view and manage its resources, such as disks,
network interfaces, and extensions.

Provisioning a VM in Azure allows you to create a virtualized
environment in the cloud that you can use to host applications and
services. Azure VMs offer a range of options for configuring the
hardware and software resources of the virtual machine, giving you the
flexibility to create a VM that meets your specific needs. Once the
virtual machine has been created, you can connect to it using HTTP (80),
HTTPS(443), SSH(22) and Remote Desktop Protocol (RDP).

## Connecting Azure Virtual machine using Remote Desktop Protocol

To connect to an Azure virtual machine using Remote Desktop Protocol
(RDP), [follow these steps here](https://learn.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal#connect-to-virtual-machine) 


Note: If you are using a Windows virtual machine, you will need to
enable Remote Desktop connections on the virtual machine before you can
connect to it using RDP. To do this, follow these steps:

1.  In the Azure portal, navigate to the virtual machine that you want
    to connect to.

2.  Under \"Settings\", click \"Operating system\".

3.  Under \"Remote Desktop\", toggle the switch to \"On\".

4.  Click \"Save\" to apply the changes.

## Testing our Azure Virtual Machine using a Web Server

Depending on the operating system of the VM, you may need to install a
web server manually. For example, on Windows VMs, you can install
web-server via windows Powershell. On Linux VMs, you can install Apache
or another web server using the package manager. [more info here](https://learn.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal#install-web-server)

## Creating and Running a React -App on Azure Virtual Machine
1. Create an Azure virtual machine and connect to it using Remote Desktop Protocol (RDP) or Secure Shell (SSH).
2. Install Node.js on the virtual machine by following the instructions for your operating system. You can download the latest version of Node.js from the [official website](https://nodejs.org/) or use a package manager like apt or yum to install it.
3. Install Create React App by running the following command:npm install -g create-react-app
This will install Create React App globally, which will allow you to create new React projects from the command line.

4. Create a new React app by running the following command: create-react-app my-app
Replace "my-app" with the desired name for your app. This will create a new directory with the same name as your app and generate the files and dependencies needed for a basic React app.
5. Navigate to the app's directory: cd my-app
Start the development server by running: npm start

To access a React app running locally on an Azure virtual machine, you will need to know the public IP address or domain name of the virtual machine and the port on which the app is running.

Assuming that the app is running on port 3000 and the virtual machine's public IP address is 123.456.789.0, you can access the app by navigating to http://123.456.789.0:3000 in a web browser.

If you are accessing the app from a device on the same network as the virtual machine, you can also use the private IP address of the virtual machine. You can find the private IP address by running the ipconfig command in a terminal on the virtual machine.

If you want to access the app from a device outside of the virtual machine's network, you may need to configure the virtual machine's firewall to allow incoming traffic on the port that the app is running on. You can do this through the Azure portal or using the az command-line tool.
It's also possible to use a tool like [ngrok](https://ngrok.com/) to create a secure tunnel to your local development environment, which can make it easier to access the app from external devices.

## Conclusion

In conclusion, Azure Virtual Machines (VMs) are a powerful and flexible
solution for hosting applications and services in the cloud. They offer
a range of options for configuring the hardware and software resources
of the virtual machine, including the operating system, CPU, memory, and
storage.

By using the Azure portal, you can create, configure, and manage Azure
VMs with ease. You can use Remote Desktop Protocol (RDP) to connect to
the VM and access the operating system, allowing you to install and
configure a web server or other applications.

Azure VMs offer many benefits, including scalability, reliability, and
security. They can be used to host a wide range of applications and
services, including web servers, databases, and analytics platforms.
With Azure VMs, you can take advantage of the power and flexibility of
the Azure platform to build and deploy your applications and services in
the cloud. So, Azure VMs can be a great solution for many different
scenarios.

Credit to Microsoft Learn Platform
More information read the docs on
<https://learn.microsoft.com/en-us/azure/virtual-machines/>.You can also
attend Azure virtual Training day on
<https://www.microsoft.com/en-us/trainingdays/azure> to get an in-depth
fundamentals of cloud computing concepts. You'll also learn the basics
of infrastructure as a service (IaaS), platform as a service (PaaS), and
software as a service (SaaS).This will help you Take the [Microsoft
Azure Fundamentals certification
exam](https://docs.microsoft.com/learn/certifications/azure-fundamentals/) at
no cost.
