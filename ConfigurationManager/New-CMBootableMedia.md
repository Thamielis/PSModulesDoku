New-CMBootableMedia
-------------------




### Synopsis
Create bootable media.



---


### Description

This cmdlet creates media used to deploy an OS. Bootable media contains the boot image, optional prestart commands and associated files, and Configuration Manager files. Use bootable media to install a new version of Windows on a new computer (bare metal), or to replace an existing computer and transfer settings.



> [!NOTE] > This cmdlet requires elevated permissions to run.



For more information, see Task sequence media overview (/mem/configmgr/osd/deploy-use/create-task-sequence-media).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDistributionPoint](Get-CMDistributionPoint)



* [Get-CMManagementPoint](Get-CMManagementPoint)



* [Get-CMPackage](Get-CMPackage)



* [New-CMPrestageMedia](New-CMPrestageMedia)



* [New-CMCaptureMedia](New-CMCaptureMedia)



* [New-CMStandaloneMedia](New-CMStandaloneMedia)





---


### Examples
#### Example 1: Create bootable media
```PowerShell
$BootImage = Get-CMBootImage -Name "Boot image (x64)"
$DistributionPoint = Get-CMDistributionPoint -SiteCode CM1
$ManagementPoint = Get-CMManagementPoint -SiteSystemServerName "SiteSystemServer02.Contoso.com"

New-CMBootableMedia -MediaMode Dynamic -MediaType CdDvd -Path "\\Server\share\test.iso" -AllowUnknownMachine -BootImage $BootImage -DistributionPoint $DistributionPoint -ManagementPoint $ManagementPoint
```



---


### Parameters
#### **AllowUacPrompt**

Add this parameter to allow Windows to prompt you to elevate your administrator permissions with User Account Control (UAC). This cmdlet requires elevated permissions to run.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **AllowUnattended**

Add this parameter to allow an unattended OS deployment. An unattended OS deployment doesn't prompt for network configuration or optional task sequences.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **AllowUnknownMachine**

Add this parameter to allow Configuration Manager to provision unknown computers. An unknown computer is a computer that the site hasn't discovered yet.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **BootImage**

Specify a boot image object. To get this object, use the Get-CMBootImage (Get-CMBootImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases         |
|-----------------|--------|--------|-------------|----------------|
|`[IResultObject]`|true    |named   |False        |BootImagePackage|



#### **CertificateExpireTime**

If you create a self-signed media certificate for HTTP communication, this parameter specifies the certificate's expiration date and time. Specify a datetime sufficiently in the future. When this certificate expires, you can't use the bootable media. Use the -CertificateStartTime parameter to set the start date.


For example:






$date = [datetime]::parseexact("11/16/2021", 'MM/dd/yyyy', $null)







|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **CertificatePassword**

If you use the -CertificatePath parameter to import a PKI certificate for HTTPS communication, use this parameter to specify the password for the certificate file.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **CertificatePath**

Specify the path to a PKI certificate to import. Use the -CertificatePassword parameter to specify the password for this certificate file. Use these parameters if you configure the site for HTTPS client communication.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CertificateStartTime**

To create a self-signed certificate for HTTP communication, this parameter specifies the certificate's start date and time. Use the -CertificateExpireTime parameter to set the expiration date. You can't use the bootable media until this date.


For example:






$date = [datetime]::parseexact("11/16/2020", 'MM/dd/yyyy', $null)







|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPoint**

Specify one or more distribution point objects to which you distributed the boot image. To get this object, use the Get-CMDistributionPoint (Get-CMDistributionPoint.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|true    |named   |False        |DistributionPoints|



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FormatMedia**

If the MediaType is `Usb`, you can add this parameter to format the removable USB drive as FAT32, and make it bootable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ManagementPoint**

Specify one or more management point objects that the media uses in initial communication. Use the -MediaMode parameter to determine how the media communicates when it runs. To get this object, use the Get-CMManagementPoint (Get-CMManagementPoint.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases         |
|-------------------|--------|--------|-------------|----------------|
|`[IResultObject[]]`|true    |named   |False        |ManagementPoints|



#### **MediaMode**

Specify how the client finds a management point to get deployment information:


* `Dynamic`: The media contacts a management point, which redirects the client to a different management point based on the client location in the site boundaries.


* `SiteBased`: The media communicates the management point specified with the -ManagementPoint parameter.



Valid Values:

* Dynamic
* SiteBased






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[MediaMode]`|true    |named   |False        |



#### **MediaPassword**

Specify a secure string password to protect the task sequence media. When you boot a device with this media, you have to enter the password to continue.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **MediaType**

Specify whether the media is a CD/DVD set or a removable USB drive.



Valid Values:

* Usb
* CdDvd
* Hd






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[MediaInputType]`|true    |named   |False        |



#### **NoAutoRun**

Add this parameter to include the autorun.inf file on the media. Configuration Manager doesn't add it by default. This file is commonly blocked by antimalware products. For more information on the AutoRun feature of Windows, see Creating an AutoRun-enabled CD-ROM Application (/windows/desktop/shell/autoplay). If still necessary for your scenario, add this parameter to include the file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

If the MediaType is `CdDvd`, specify the name and path where Configuration Manager writes the output files. For example, `C:\output\boot.iso`.






|Type      |Required|Position|PipelineInput|Aliases                               |
|----------|--------|--------|-------------|--------------------------------------|
|`[String]`|true    |named   |False        |MediaPath<br/>OutputPath<br/>DriveName|



#### **PrestartCommand**

Specify a prestart command that runs before the task sequence. A prestart command is a script or an executable that can interact with the user in Windows PE before the task sequence runs to install the OS. If the command isn't native to Windows PE, use the PrestartPackage to include files for the command.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|false   |named   |False        |PreExecCommandLine|



#### **PrestartPackage**

If you use the PrestartCommand parameter, use this parameter to specify a package that contains files for the prestart command. To get the package object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **SiteCode**

Applies to version 2010 and later. Use this parameter with the ManagementPoint parameter to specify the site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TemporaryFolder**

The media creation process can require much temporary drive space. By default, Configuration Manager uses the temporary directory of the current user: `$env:temp`. For example, `C:\Users\jqpublic\AppData\Local\Temp`. To give you greater flexibility with where to store these temporary files, specify a custom location for staging temporary data.






|Type      |Required|Position|PipelineInput|Aliases                           |
|----------|--------|--------|-------------|----------------------------------|
|`[String]`|false   |named   |False        |TemporaryDirectory<br/>StagingArea|



#### **UserDeviceAffinity**

To support user-centric management in Configuration Manager, specify how you want the media to associate users with the destination computer. For more information about how OS deployment supports user device affinity, see Associate users with a destination computer (/mem/configmgr/osd/get-started/associate-users-with-a-destination-computer).


* `DoNotAllow`: Don't allow user device affinity. The media doesn't associate users with the destination computer. In this scenario, the task sequence doesn't associate users with the destination computer when it deploys the OS.


* `AdministratorApproval`: Allow user device affinity pending administrator approval. The media associates users with the destination computer after you grant approval. This functionality is based on the scope of the task sequence that deploys the OS. In this scenario, the task sequence creates a relationship between the specified users and the destination computer. It then waits for approval from an administrative user before it deploys the OS.


* `AutoApproval`: Allow user device affinity with auto-approval. The media automatically associates users with the destination computer. This functionality is based on the actions of the task sequence that deploys the OS. In this scenario, the task sequence creates a relationship between the specified users and destination computer when it deploys the OS to the destination computer.



Valid Values:

* DoNotAllow
* AdministratorApproval
* AutoApproval






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[UserDeviceAffinityType]`|false   |named   |False        |



#### **Variable**

Specify one or more task sequence variables and values in a hashtable. A task sequence variable is a name/value pair that is used during the task sequence deployment.






|Type         |Required|Position|PipelineInput|Aliases                            |
|-------------|--------|--------|-------------|-----------------------------------|
|`[Hashtable]`|false   |named   |False        |TaskSequenceVariables<br/>Variables|



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMBootableMedia [-AllowUacPrompt] [-AllowUnattended] [-AllowUnknownMachine] -BootImage <IResultObject> [-CertificateExpireTime <DateTime>] [-CertificatePassword <SecureString>] [-CertificatePath <String>] [-CertificateStartTime <DateTime>] [-DisableWildcardHandling] -DistributionPoint <IResultObject[]> [-Force] [-ForceWildcardHandling] [-FormatMedia] -ManagementPoint <IResultObject[]> -MediaMode {Dynamic | SiteBased} [-MediaPassword <SecureString>] -MediaType {Usb | CdDvd} [-NoAutoRun] -Path <String> [-PrestartCommand <String>] [-PrestartPackage <IResultObject>] [-SiteCode <String>] [-TemporaryFolder <String>] [-UserDeviceAffinity {DoNotAllow | AdministratorApproval | AutoApproval}] [-Variable <Hashtable>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
