# osTicket-extended-setup
A granular guide detailing the step-by-step process of setting up osTicket within an Azure environment, designed for those seeking comprehensive installation instructions.

--------------------------

![image](https://github.com/GrifCodes/osTicket-extended-setup/assets/150773923/509b522a-6099-4ea1-ba47-b74d0185904c)


# osTicket Detailed Setup Guide

This guide offers a comprehensive walkthrough for setting up osTicket on a virtual machine within an Azure environment, with extra detail provided for the more complex steps.

## Prerequisites

- An Azure account with active subscription.
- osTicket Installation Files from [Google Drive](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6).

## Part 1: Create Virtual Machine in Azure

Create a Resource Group and VM to host osTicket.

### Detailed Steps:
1. In the Azure portal, create a new resource group for organizational purposes.
2. Deploy a Windows 10 VM with 2-4 Virtual CPUs, and note the automatically created Vnet.

## Part 2: osTicket Installation

Install IIS, PHP, MySQL, and osTicket onto the VM.

### Detailed Steps:
1. After VM deployment, connect via RDP and open Server Manager.
2. Add the Web Server (IIS) role with CGI under Application Development to support PHP.
3. Use PHP Manager for IIS to configure PHP settings.
4. For MySQL, ensure you use version 5.5.62 for compatibility, and take note of the root password set during installation.
5. Download osTicket from the provided link, extract the contents, and configure it within the IIS web root directory, typically `C:\inetpub\wwwroot`.

## Part 3: Post Installation Setup

Configure roles, agents, and departments within osTicket.

### Detailed Steps:
- Navigate to osTicket's admin panel to define user roles and assign agents to departments.
- Details on setting permissions and organizing teams are crucial for future administration and are provided in the setup guide.

## Part 4: Tickets and Ticket Lifecycle

Practice managing the ticket lifecycle from creation to resolution.

### Detailed Steps:
- Create sample tickets and run through the resolution process to understand the osTicket workflow. Pay particular attention to the assignment and closure of tickets.

## Cleanup and Final Steps

Finalize the installation by removing the setup directory and securing configuration files.

### Detailed Steps:
- Deleting the `setup` folder from the osTicket installation directory is a critical security measure.
- Adjust file permissions on `ost-config.php` to prevent unauthorized changes.

## Troubleshooting

Address common issues such as page load errors, database connections, and file permissions.

### Detailed Troubleshooting:
- **Issue**: IIS not serving osTicket pages.
  - **Detailed Solution**: Verify that the IIS service is running and that PHP is configured correctly through PHP Manager. Ensure that the osTicket web application is properly set up in IIS.
- **Issue**: Can't connect to the MySQL database.
  - **Detailed Solution**: Confirm that MySQL Server is running and that the service isn't blocked by Windows Firewall. Check the connection strings in `ost-config.php` for accuracy.

## Conclusion

This guide is designed to demystify the osTicket setup process, providing clarity on the more intricate steps while offering direct instructions for the more straightforward tasks.
For additional guidance, refer to the [official osTicket documentation](https://osticket.com/wiki/Installation).

