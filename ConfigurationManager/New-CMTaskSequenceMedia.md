New-CMTaskSequenceMedia
-----------------------




### Synopsis
Creates task sequence media in Configuration Manager.



---


### Description

The New-CMTaskSequenceMedia cmdlet creates task sequence media in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTaskSequence](Get-CMTaskSequence)





---


### Examples
#### Example 1: Create task sequence media with the captured media option
```PowerShell
PS XYZ:\> New-CMTaskSequenceMedia -CaptureMediaOption -MediaPath "\\Contoso320\Users\Administrator.Contoso319DOM\Desktop\DD\1.iso" -MediaInputType CDDVD -BootImageName "Boot" -DistributionPointServerName "Contoso320.Contoso319DOM.NET"
```
This command creates task sequence media by specifying the CaptureMediaOption parameter. The command also specifies a value for the MediaPath parameter, and a value for the MediaInputType parameter.
#### Example 2: Create task sequence media with the standalone media option
```PowerShell
PS XYZ:\> $Group = @{"6"="8";}
PS XYZ:\> New-CMTaskSequenceMedia -StandAloneMediaOption -Variable $Group -MediaInputType CDDVD -MediaPath "\\Contoso320\Users\Administrator.Contoso319DOM\Desktop\DD\111 - Copy.iso" -ProtectPassword 0 -TaskSequenceId "CCC0000B" -TaskSequenceDistributionPointServerName "\\Contoso320.Contoso319DOM.NET"
```
The first command creates a mapping, and then stores the result in the $Group variable.


The second command creates task sequence media by specifying the StandAloneMediaOption parameter.
#### Example 3: Create task sequence media with the bootable media option
```PowerShell
PS XYZ:\> New-CMTaskSequenceMedia -BootableMediaOption -MediaInputType CDDVD -MediaPath "\\Contoso320\Users\Administrator.Contoso319DOM\Desktop\DD\111 - Copy (6).iso" -MediaMode Dynamic -ProtectPassword 0 -BootImageName "boot" -DistributionPointServerName "Contoso320.Contoso319DOM.NET" -ManagementnPointNetworkOperatingSystemPath "Contoso320.Contoso319DOM.NET"
```
This command creates task sequence media by specifying the BootableMediaOption parameter.
#### Example 4: Create task sequence media with the prestaged media option
```PowerShell
PS XYZ:\> New-CMTaskSequenceMedia -PrestagedMediaOption -MediaMode Dynamic -MediaPath "\\Contoso320\Users\Administrator.Contoso319DOM\Desktop\DD\2.wim"  -ProtectPassword 0 -TaskSequenceId "CCC0000B" -BootImageName "boot" -DistributionPointServerName "Contoso320.Contoso319DOM.NET" -ManagementnPointNetworkOperatingSystemPath "Contoso320.Contoso319DOM.NET" -OperatingSystemImageDistributionPointServerName "Contoso320.Contoso319DOM.NET" -TaskSequenceDistributionPointServerName "\\Contoso320.Contoso319DOM.NET"
```
This command uses the New-CMTaskSequenceMedia cmdlet to create task sequence media by specifying the PrestagedMediaOption parameter.


---


### Parameters
#### **AllowUacPrompt**

Indicates that User Account Control (UAC) prompts are allowed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **AllowUnattendedDeployment**

Indicates whether you allow unattended operating system deployment, which does not prompt for network configuration or optional task sequences.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Application**

Specifies applications included in the task sequence.






|Type               |Required|Position|PipelineInput |Aliases     |
|-------------------|--------|--------|--------------|------------|
|`[IResultObject[]]`|false   |named   |True (ByValue)|Applications|



#### **ApplicationName**

Specifies an array of names of applications included in the task sequence.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **BootableMedia**








|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[Switch]`|true    |named   |False        |BootableMediaOption|



#### **BootImage**

Specifies a boot image object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **BootImageDistributionPoint**

Specifies a boot image distribution point.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **BootImageDistributionPointServerName**

Specifies a boot image distribution point server name.






|Type      |Required|Position|PipelineInput|Aliases                    |
|----------|--------|--------|-------------|---------------------------|
|`[String]`|true    |named   |False        |DistributionPointServerName|



#### **BootImageId**

Specifies the ID of the boot image package associated with the task sequence media.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BootImageManagementPoint**

Specifies a boot image management point.






|Type               |Required|Position|PipelineInput |Aliases                  |
|-------------------|--------|--------|--------------|-------------------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|BootImageManagementPoints|



#### **BootImageManagementPointServerName**

Specifies a boot image management point server name.






|Type        |Required|Position|PipelineInput|Aliases                                                          |
|------------|--------|--------|-------------|-----------------------------------------------------------------|
|`[String[]]`|true    |named   |False        |ManagementPointServerName<br/>BootImageManagementPointServerNames|



#### **CaptureMedia**








|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Switch]`|true    |named   |False        |CaptureMediaOption|



#### **CommandDistributionPointServerName**

Specifies a name for a distribution point server from which the cmdlet acquires the package. The CommandPackageName parameter specifies the package name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CommandIncludeFile**

Indicates whether to include a file.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CommandPackage**

Specifies a command package.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CommandPackageDistributionPoint**

Specifies a command package distrubtion point.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CommandPackageName**

Specifies a package name for the command specified by the CommandLine parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specifies a comment for a prestaged media file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CreatedBy**

Specifies the name of an individual or organization responsible for the creation of the prestaged media.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CreateMediaSelfCertificate**

Indicates whether the media includes a self-signed certificate. Use this parameter only in mixed-mode environments.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DriveName**

Specifies a drive name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DriverPackage**

Specifies a driver package.






|Type               |Required|Position|PipelineInput |Aliases                                            |
|-------------------|--------|--------|--------------|---------------------------------------------------|
|`[IResultObject[]]`|false   |named   |True (ByValue)|DriverPackages<br/>PackageDriver<br/>PackageDrivers|



#### **DriverPackageName**

Specifies the name of a driver package.






|Type        |Required|Position|PipelineInput|Aliases          |
|------------|--------|--------|-------------|-----------------|
|`[String[]]`|false   |named   |False        |PackageDriverName|



#### **EnablePrestartCommand**

Indicates whether to enable a prestart command. A prestart command is a script or executable that runs before the task sequence.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUnknownSupport**

Indicates whether to provision unknown systems for operating system deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ExpirationDate**

Specifies an expiration date, in D.HH:MM:SS format, for bootable media.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ImportCertificatePassword**

Specifies a password for an import certificate, as a secure string. An import certificate is a PKI-issued certificate added to the boot media for client authentication and communication with a Configuration Manager site.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **ImportCertificatePath**

Specifies a path for an import certificate to add to the boot media.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **IncludeApplicationDependency**

Indicates that the cmdlet detects associated application dependencies and adds them to this media.






|Type       |Required|Position|PipelineInput|Aliases                       |
|-----------|--------|--------|-------------|------------------------------|
|`[Boolean]`|false   |named   |False        |IncludeApplicationDependencies|



#### **MediaInputType**

Specifies a media input type. The acceptable values for this parameter are:


* CDDVD


* USB



Valid Values:

* Usb
* CdDvd
* Hd






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[MediaInputType]`|true    |named   |False        |



#### **MediaMode**

Specifies a media mode. The acceptable values for this parameter are:


* Dynamic


* SiteBased



Valid Values:

* Dynamic
* SiteBased






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[MediaMode]`|true    |named   |False        |



#### **MediaPath**

Specifies a path to the media.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **MediaSize**

Specifies the size of the media. The acceptable values for this parameter are:


* None


* Size4GB


* Size650MB


* Size8GB


* SizeUnlimited



Valid Values:

* None
* Size650MB
* Size4GB
* Size8GB
* SizeUnlimited






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[MediaSize]`|false   |named   |False        |



#### **OperatingSystemImageDistributionPoint**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **OperatingSystemImageDistributionPointServerName**

Specifies the name of a distribution point server for an operating system image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **OperatingSystemImageName**

Specifies the name of an operating system image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OperatingSystemImagePackage**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|false   |named   |True (ByValue)|



#### **OperatingSystemImagePackageId**

Specifies the identifier of an operating system image package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Package**

Specifies package objects.






|Type               |Required|Position|PipelineInput |Aliases |
|-------------------|--------|--------|--------------|--------|
|`[IResultObject[]]`|false   |named   |True (ByValue)|Packages|



#### **PackageName**

Specifies an array of package names.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **Password**

Specifies a password, as a secure string.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **PrestagedMedia**








|Type      |Required|Position|PipelineInput|Aliases                               |
|----------|--------|--------|-------------|--------------------------------------|
|`[Switch]`|true    |named   |False        |PrestagedMediaOption<br/>PrestageMedia|



#### **PrestartCommandLine**

Specifies a pre-start command line.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |CommandLine|



#### **ProtectPassword**

Indicates whether to protect the media with a password.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|true    |named   |False        |



#### **StandaloneMedia**








|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[Switch]`|true    |named   |False        |StandAloneMediaOption|



#### **StartDate**

Specifies a start date and time, in D.HH:MM:SS format.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **TaskSequence**

Specifies a task sequence object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **TaskSequenceDistributionPoint**

Specifies a task sequence distribution point.






|Type               |Required|Position|PipelineInput |Aliases                       |
|-------------------|--------|--------|--------------|------------------------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|TaskSequenceDistributionPoints|



#### **TaskSequenceDistributionPointServerName**

Specifies an array of available distribution point servers for a task sequence.






|Type        |Required|Position|PipelineInput|Aliases                                 |
|------------|--------|--------|-------------|----------------------------------------|
|`[String[]]`|true    |named   |False        |TaskSequenceDistributionPointServerNames|



#### **TaskSequenceId**

Specifies an ID for a task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **UserDeviceAffinity**

Specifies user device affinity. User device affinity associates users with a destination computer. The acceptable values for this parameter are:


* AdministratorApproval


* AutoApproval


* DoNotAllow



Valid Values:

* DoNotAllow
* AdministratorApproval
* AutoApproval






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[UserDeviceAffinityType]`|false   |named   |False        |



#### **Variable**

Specifies a task sequence variable. The task sequence variable consists of a name and a value.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



#### **Version**

Specifies the version information for the media.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]



Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* 






---


### Notes




---


### Syntax
```PowerShell
New-CMTaskSequenceMedia [-AllowUacPrompt] [-AllowUnattendedDeployment <Boolean>] -BootableMedia -BootImageDistributionPointServerName <String> -BootImageId <String> -BootImageManagementPointServerName <String[]> [-CommandDistributionPointServerName <String>] [-CommandIncludeFile <Boolean>] [-CommandPackageName <String>] [-CreateMediaSelfCertificate <Boolean>] [-DisableWildcardHandling] [-DriveName <String>] [-EnablePrestartCommand <Boolean>] [-EnableUnknownSupport <Boolean>] [-ExpirationDate <DateTime>] [-ForceWildcardHandling] [-ImportCertificatePassword <SecureString>] [-ImportCertificatePath <String>] -MediaInputType {Usb | CdDvd | Hd | Usb | CdDvd | Hd} -MediaMode {Dynamic | SiteBased | Dynamic | SiteBased} -MediaPath <String> [-MediaSize {None | Size650MB | Size4GB | Size8GB | SizeUnlimited}] [-Password <SecureString>] [-PrestartCommandLine <String>] -ProtectPassword <Boolean> [-StartDate <DateTime>] [-UserDeviceAffinity {DoNotAllow | AdministratorApproval | AutoApproval}] [-Variable <Hashtable>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequenceMedia [-AllowUacPrompt] [-AllowUnattendedDeployment <Boolean>] [-CommandDistributionPointServerName <String>] [-CommandIncludeFile <Boolean>] [-CommandPackageName <String>] [-DisableWildcardHandling] [-DriveName <String>] [-EnablePrestartCommand <Boolean>] [-ForceWildcardHandling] [-IncludeApplicationDependency <Boolean>] -MediaInputType {Usb | CdDvd | Hd | Usb | CdDvd | Hd} -MediaPath <String> [-MediaSize {None | Size650MB | Size4GB | Size8GB | SizeUnlimited}] [-Password <SecureString>] [-PrestartCommandLine <String>] -ProtectPassword <Boolean> -StandaloneMedia -TaskSequenceDistributionPointServerName <String[]> -TaskSequenceId <String> [-Variable <Hashtable>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequenceMedia [-AllowUacPrompt] [-AllowUnattendedDeployment <Boolean>] [-CommandIncludeFile <Boolean>] [-CommandPackage <IResultObject>] [-CommandPackageDistributionPoint <IResultObject>] [-DisableWildcardHandling] [-DriveName <String>] [-EnablePrestartCommand <Boolean>] [-ForceWildcardHandling] [-IncludeApplicationDependency <Boolean>] [-MediaInputType {Usb | CdDvd | Hd | Usb | CdDvd | Hd}] -MediaPath <String> [-MediaSize {None | Size650MB | Size4GB | Size8GB | SizeUnlimited}] [-Password <SecureString>] [-PrestartCommandLine <String>] [-ProtectPassword <Boolean>] -StandaloneMedia -TaskSequence <IResultObject> -TaskSequenceDistributionPoint <IResultObject[]> [-Variable <Hashtable>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequenceMedia [-AllowUacPrompt] [-AllowUnattendedDeployment <Boolean>] -BootableMedia -BootImage <IResultObject> -BootImageDistributionPoint <IResultObject> -BootImageManagementPoint <IResultObject[]> [-CommandIncludeFile <Boolean>] [-CommandPackage <IResultObject>] [-CommandPackageDistributionPoint <IResultObject>] [-CreateMediaSelfCertificate <Boolean>] [-DisableWildcardHandling] [-DriveName <String>] [-EnablePrestartCommand <Boolean>] [-EnableUnknownSupport <Boolean>] [-ExpirationDate <DateTime>] [-ForceWildcardHandling] [-ImportCertificatePassword <SecureString>] [-ImportCertificatePath <String>] [-MediaInputType {Usb | CdDvd | Hd | Usb | CdDvd | Hd}] [-MediaMode {Dynamic | SiteBased | Dynamic | SiteBased}] -MediaPath <String> [-MediaSize {None | Size650MB | Size4GB | Size8GB | SizeUnlimited}] [-Password <SecureString>] [-PrestartCommandLine <String>] [-ProtectPassword <Boolean>] [-StartDate <DateTime>] [-UserDeviceAffinity {DoNotAllow | AdministratorApproval | AutoApproval}] [-Variable <Hashtable>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequenceMedia [-AllowUacPrompt] [-AllowUnattendedDeployment <Boolean>] [-Application <IResultObject[]>] [-ApplicationName <String[]>] -BootImageDistributionPointServerName <String> -BootImageId <String> -BootImageManagementPointServerName <String[]> [-CommandDistributionPointServerName <String>] [-CommandIncludeFile <Boolean>] [-CommandPackageName <String>] [-Comment <String>] [-CreatedBy <String>] [-DisableWildcardHandling] [-DriverPackage <IResultObject[]>] [-DriverPackageName <String[]>] [-ForceWildcardHandling] -MediaMode {Dynamic | SiteBased | Dynamic | SiteBased} -MediaPath <String> -OperatingSystemImageDistributionPointServerName <String> [-OperatingSystemImageName <String>] [-OperatingSystemImagePackageId <String>] [-Package <IResultObject[]>] [-PackageName <String[]>] -PrestagedMedia [-PrestartCommandLine <String>] -ProtectPassword <Boolean> -TaskSequenceDistributionPointServerName <String[]> -TaskSequenceId <String> [-Variable <Hashtable>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequenceMedia [-AllowUacPrompt] [-AllowUnattendedDeployment <Boolean>] [-Application <IResultObject[]>] -BootImage <IResultObject> -BootImageDistributionPoint <IResultObject> -BootImageManagementPoint <IResultObject[]> [-CommandIncludeFile <Boolean>] [-CommandPackage <IResultObject>] [-CommandPackageDistributionPoint <IResultObject>] [-Comment <String>] [-CreatedBy <String>] [-DisableWildcardHandling] [-DriverPackage <IResultObject[]>] [-ForceWildcardHandling] -MediaMode {Dynamic | SiteBased | Dynamic | SiteBased} -MediaPath <String> -OperatingSystemImageDistributionPoint <IResultObject> [-OperatingSystemImagePackage <IResultObject>] [-Package <IResultObject[]>] -PrestagedMedia [-PrestartCommandLine <String>] [-ProtectPassword <Boolean>] -TaskSequence <IResultObject> -TaskSequenceDistributionPoint <IResultObject[]> [-Variable <Hashtable>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequenceMedia [-AllowUacPrompt] -BootImage <IResultObject> -BootImageDistributionPoint <IResultObject> -CaptureMedia [-DisableWildcardHandling] [-DriveName <String>] [-ForceWildcardHandling] [-MediaInputType {Usb | CdDvd | Hd | Usb | CdDvd | Hd}] -MediaPath <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequenceMedia [-AllowUacPrompt] -BootImageDistributionPointServerName <String> -BootImageId <String> -CaptureMedia [-DisableWildcardHandling] [-DriveName <String>] [-ForceWildcardHandling] -MediaInputType {Usb | CdDvd | Hd | Usb | CdDvd | Hd} -MediaPath <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
