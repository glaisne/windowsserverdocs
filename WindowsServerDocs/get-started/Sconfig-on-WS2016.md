---
title: Configure a Server Core installation of Windows Server with Sconfig.cmd
description: "Explains how to use Sconfig.cmd" 
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.date: 10/17/2017
ms.technology: server-general
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e6cac074-c6fc-46dd-9664-fa0342c0a5e8
author: jaimeo
ms.author: jaimeo
manager: dongill
ms.localizationpriority: medium
---
# Configure a Server Core installation of Windows Server 2016 or Windows Server, version 1709, with Sconfig.cmd
> Applies To: Windows Server (Semi-Annual Channel) and Windows Server 2016

In Windows Server 2016 and Windows Server, version 1709, you can use the Server Configuration tool (Sconfig.cmd) to configure and manage several common aspects of Server Core installations. You must be a member of the Administrators group to use the tool.  

You can use Sconfig.cmd in Server Core and Server with Desktop Experience (Windows Server 2016 only) installations. 

## Start the Server Configuration Tool  

1. Change to the system drive.  

2. Type `Sconfig.cmd`, and then press ENTER. The Server Configuration tool interface opens:  

   <img src="mainsconfigpage.png" style='float:left; padding:.5em;' alt="Screenshot of Sconfig.cmd user interface"><br/>Screenshot of Sconfig.cmd user interface<br/>
   ##  <a name="BKMK_Domainworkgroup"></a> Domain/Workgroup settings<br/> The current Domain/Workgroup settings are displayed in the default Server Configuration tool screen. You can join a domain or a workgroup by accessing the <strong>Domain/Workgroup</strong> settings page from the main menu and following the instructions on the following pages, supplying any required information.<br/>
   If a domain user has not been added to the local administrators group, you will not be able to make system changes, such as changing the computer name, by using the domain user. To add a domain user to the local administrators group, allow the computer to restart. Next, log on to the computer as the local administrator and follow the steps in the <a href="assetId:///3c2f8ca4-6adc-4ebd-8daf-eb0de16c2c7d#BKMK_Localadministratorsettings" data-raw-source="[Local administrator settings](assetId:///3c2f8ca4-6adc-4ebd-8daf-eb0de16c2c7d#BKMK_Localadministratorsettings)">Local administrator settings</a> section later in this document.<br/>
   &gt; [!NOTE]
   &gt;  You are required to restart the server to apply any changes to domain or workgroup membership. However, you can make additional changes and restart the server after all of the changes to avoid the need to restart the server multiple times. By default, running virtual machines are automatically saved prior to restarting the Hyper-V Server.<br/>
   ## Computer name settings<br/> The current computer name is displayed in the default Server Configuration Tool screen. You can change the computer name by accessing the “Computer Name” settings page from the main menu and following the instructions.<br/>
   &gt; [!NOTE]
   &gt;  You are required to restart the server to apply any changes to domain or workgroup membership. However, you can make additional changes and restart the server after all of the changes to avoid the need to restart the server multiple times. By default, running virtual machines are automatically saved prior to restarting the Hyper-V Server.<br/>
   ##  <a name="BKMK_Localadministratorsettings"></a> Local administrator settings<br/> To add additional users to the local administrators group, use the <strong>Add Local Administrator</strong> option on the main menu. On a domain joined machine, enter the user in the following format: domain\username. On a non-domain joined machine (workgroup machine), enter only the user name. The changes take effect immediately.<br/>
   ## Network settings<br/> You can configure the IP address to be assigned automatically by a DHCP Server or you can assign a static IP address manually. This option allows you to configure DNS Server settings for the server as well.<br/>
   &gt; [!NOTE]
   &gt;  These options and many more are now available using the Networking Windows PowerShell cmdlets. For more information, see <a href="https://technet.microsoft.com/library/jj134956.aspx" data-raw-source="[Network Adapter Cmdlets](https://technet.microsoft.com/library/jj134956.aspx)">Network Adapter Cmdlets</a> in the Windows Server Library.<br/>
   ## Windows Update settings<br/> The current Windows Update settings are displayed in the default Server Configuration Tool screen. You can configure the server to use Automatic or Manual updates on the <strong>Windows Update Settings</strong> configuration option on the main menu.<br/>
   When <strong>Automatic Updates</strong> are selected, the system will check for and install updates every day at 3:00 AM. The settings take effect immediately. When <strong>Manual</strong> updates are selected, the system will not check for updates automatically.<br/>
   At any time, you can download and install applicable updates from the <strong>Download and Install Updates</strong> option on the main menu.

   The **Download Only** option will scan for updates, download any that are available, and then notify you in the Action Center that they are ready for installation. This is default option.  

## Remote Desktop settings  
 The current status of remote desktop settings is displayed in the default Server Configuration Tool screen. You can configure the following Remote Desktop settings by accessing the **Remote Desktop** main menu option and following the instructions on screen.  

-   Enable Remote Desktop for Clients running Remote Desktop with Network Level Authentication  

-   Enable Remote Desktop for clients running any version of Remote Desktop  

-   Disable Remote  

## Date and time settings  
 You can access and change date and time settings by accessing the **Date and Time** main menu option 

## Telemetry settings
This option lets you configure what data is sent to Microsoft.

## Windows Activation settings
This option lets you configure Windows Activation.

## To enable remote management  
You can enable various remote management scenarios from the **Configure Remote Management** main menu option:  

-   Microsoft Management Console remote management  
-   Windows PowerShell  
-   Server Manager  

## To log off, restart, or shut down the server  
 To log off, restart, or shut down the server, access the corresponding menu item from the main menu. These options are also available from the Windows Security menu which can be accessed from any application at any time by pressing CTRL+ALT+DEL.  

## To exit to the command line  
 Select the **Exit to the Command Line** option and press ENTER to exit to the command line. To return to the Server Configuration Tool, type **Sconfig.cmd**, and then press ENTER