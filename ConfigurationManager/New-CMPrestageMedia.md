New-CMPrestageMedia
-------------------




### Synopsis
Create an OS deployment prestaged media file.



---


### Description

The New-CMPrestageMedia cmdlet creates a file to prestage an OS image on a new hard drive. For more information, see Plan prestaged media (/mem/configmgr/osd/deploy-use/create-task-sequence-media#BKMK_PlanPrestagedMedia).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplication](Get-CMApplication)



* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDistributionPoint](Get-CMDistributionPoint)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Get-CMManagementPoint](Get-CMManagementPoint)



* [Get-CMOperatingSystemImage](Get-CMOperatingSystemImage)



* [Get-CMPackage](Get-CMPackage)



* [Plan prestaged media](Plan prestaged media)





---


### Examples
#### Example 1: Create prestaged media
```PowerShell
$ManagementPoint = Get-CMManagementPoint -SiteSystemServerName "mp01.contoso.com" -SiteCode "CM1"
$BootImage = Get-CMBootImage -Name "BootImage01"
$DistributionPoint = Get-CMDistributionPoint -SiteSystemServerName "dist01.contoso.com" -SiteCode "CM1"
$OSImage = Get-CMOperatingSystemImage -Name "OSImagePkg01"

New-CMPrestageMedia -MediaMode Dynamic -Path "\\server\share\PrestagedMedia.wim" -BootImage $BootImage -DistributionPoint $DistributionPoint -ManagementPoint $ManagementPoint -OperatingSystemImage $OSImage
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



#### **Application**

Specify an array of application objects to include as part of the media file. If the task sequence references this content, it first looks locally for the content. If the content isn't in the media, the task sequence tries to download it from the network as normal. To get an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases     |
|-------------------|--------|--------|-------------|------------|
|`[IResultObject[]]`|false   |named   |False        |Applications|



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



#### **Comment**

An optional string to provide further details about the media. It's useful to describe how you configured or how you'll use this media. The maximum length is 127 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CreatedBy**

An optional string to specify who created this media, which is useful for tracking purposes. The maximum length is 50 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPoint**

Specify one or more distribution point objects to which you distributed the content for this media. To get this object, use the Get-CMDistributionPoint (Get-CMDistributionPoint.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|true    |named   |False        |DistributionPoints|



#### **DriverPackage**

Specify an array of driver package objects to include as part of the media file. If the task sequence references this content, it looks locally for the content. If the content isn't in the media, the task sequence tries to download it from the network as normal. To get this object, use the Get-CMDriverPackage (Get-CMDriverPackage.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                                            |
|-------------------|--------|--------|-------------|---------------------------------------------------|
|`[IResultObject[]]`|false   |named   |False        |DriverPackages<br/>PackageDriver<br/>PackageDrivers|



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



#### **IncludeApplicationDependency**

Add this parameter to detect associated application dependencies and add them to this media.






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[Switch]`|false   |named   |False        |IncludeApplicationDependencies|



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



#### **NoAutoRun**

Add this parameter to include the autorun.inf file on the media. Configuration Manager doesn't add it by default. This file is commonly blocked by antimalware products. For more information on the AutoRun feature of Windows, see Creating an AutoRun-enabled CD-ROM Application (/windows/desktop/shell/autoplay). If still necessary for your scenario, add this parameter to include the file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **OperatingSystemImage**

Specify an OS image package object to include for this media. Use the OperatingSystemImageIndex parameter to specify the image index in the image package. To get this object, use the Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                    |
|-----------------|--------|--------|-------------|---------------------------|
|`[IResultObject]`|true    |named   |False        |OperatingSystemImagePackage|



#### **OperatingSystemImageIndex**

Specify the image index in the image package from the OperatingSystemImage parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Package**

Specify an array of package objects to include in the media file. If the task sequence references this content, it looks locally for the content. If the content isn't in the media, the task sequence tries to download it from the network as normal. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases |
|-------------------|--------|--------|-------------|--------|
|`[IResultObject[]]`|false   |named   |False        |Packages|



#### **Path**

The path to the media file to create. The format is either a drive/directory path or a valid network path. For example:


* `C:\media\prestaged1.wim`


* `\server\share\prestaged1.wim`






|Type      |Required|Position|PipelineInput|Aliases                               |
|----------|--------|--------|-------------|--------------------------------------|
|`[String]`|true    |named   |False        |MediaPath<br/>OutputPath<br/>DriveName|



#### **PrestartCommand**

Specify a command line to run before the task sequence starts. For more information, see Prestart commands for task sequence media (/mem/configmgr/osd/understand/prestart-commands-for-task-sequence-media).






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|false   |named   |False        |PreExecCommandLine|



#### **PrestartPackage**

If you specify a PrestartCommand , use this parameter to specify a package for prestart content if needed.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **SiteCode**

Applies to version 2010 and later. Use this parameter with the ManagementPoint parameter to specify the site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequence**

Specify a task sequence object for this media to run. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



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

Specify a hashtable of task sequence variables to use during the task sequence deployment from this media.






|Type         |Required|Position|PipelineInput|Aliases                            |
|-------------|--------|--------|-------------|-----------------------------------|
|`[Hashtable]`|false   |named   |False        |TaskSequenceVariables<br/>Variables|



#### **Version**

An optional string value to specify a version for this media, which is useful for tracking and revision purposes. The maximum length is 32 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Cmdlet aliases: New-CMPrestagedMedia



---


### Syntax
```PowerShell
New-CMPrestageMedia [-AllowUacPrompt] [-AllowUnattended] [-AllowUnknownMachine] [-Application <IResultObject[]>] -BootImage <IResultObject> [-CertificateExpireTime <DateTime>] [-CertificatePassword <SecureString>] [-CertificatePath <String>] [-CertificateStartTime <DateTime>] [-Comment <String>] [-CreatedBy <String>] [-DisableWildcardHandling] -DistributionPoint <IResultObject[]> [-DriverPackage <IResultObject[]>] [-Force] [-ForceWildcardHandling] [-IncludeApplicationDependency] -ManagementPoint <IResultObject[]> -MediaMode {Dynamic | SiteBased} [-MediaPassword <SecureString>] [-NoAutoRun] -OperatingSystemImage <IResultObject> [-OperatingSystemImageIndex <Int32>] [-Package <IResultObject[]>] -Path <String> [-PrestartCommand <String>] [-PrestartPackage <IResultObject>] [-SiteCode <String>] -TaskSequence <IResultObject> [-TemporaryFolder <String>] [-UserDeviceAffinity {DoNotAllow | AdministratorApproval | AutoApproval}] [-Variable <Hashtable>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
