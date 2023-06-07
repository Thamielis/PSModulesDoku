Set-CMOperatingSystemImage
--------------------------




### Synopsis
Changes configuration settings of OS images.



---


### Description

The Set-CMOperatingSystemImage cmdlet changes configuration settings of one or more OS images in Configuration Manager. OS images are .wim format files and represent a compressed collection of reference files and folders that Configuration Manager requires to successfully install and configure an OS on a computer.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMOperatingSystemImage](Get-CMOperatingSystemImage)



* [New-CMOperatingSystemImage](New-CMOperatingSystemImage)



* [Remove-CMOperatingSystemImage](Remove-CMOperatingSystemImage)



* [Get-CMOperatingSystemImageUpdateSchedule](Get-CMOperatingSystemImageUpdateSchedule)





---


### Examples
#### Example 1: Change settings for an OS image by using an ID
```PowerShell
Set-CMOperatingSystemImage -Id "Cm10004f" -NewName "Microsoft Windows 8 (x64)" -Version "I20C" -Description "Dept02 Sys Image" -Path "\\Contoso\Public\OSD\win8x64.wim"
```

#### Example 2: Add an OS image to a security scope by using a name
```PowerShell
Set-CMOperatingSystemImage -SecurityScopeAction AddMembership -SecurityScopeName "SecScope02" -Name "ImagePkg01"
```

#### Example 3: Remove an OS image from a security scope
```PowerShell
Set-CMOperatingSystemImage -SecurityScopeAction RemoveMembership -SecurityScopeName "SecScope02" -Name "ImagePkg01"
```



---


### Parameters
#### **CopyToPackageShareOnDistributionPoint**








|Type       |Required|Position|PipelineInput|Aliases                               |
|-----------|--------|--------|-------------|--------------------------------------|
|`[Boolean]`|false   |named   |False        |CopyToPackageShareOnDistributionPoints|



#### **CustomPackageShareName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Description**

Specifies a description for the OS image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisconnectUserFromDistributionPoint**








|Type       |Required|Position|PipelineInput|Aliases                              |
|-----------|--------|--------|-------------|-------------------------------------|
|`[Boolean]`|false   |named   |False        |DisconnectUsersFromDistributionPoints|



#### **DisconnectUserFromDistributionPointMins**








|Type      |Required|Position|PipelineInput|Aliases                                     |
|----------|--------|--------|-------------|--------------------------------------------|
|`[UInt32]`|false   |named   |False        |DisconnectUsersFromDistributionPointsMinutes|



#### **DisconnectUserFromDistributionPointRetryCount**








|Type      |Required|Position|PipelineInput|Aliases                                     |
|----------|--------|--------|-------------|--------------------------------------------|
|`[UInt32]`|false   |named   |False        |DisconnectUsersFromDistributionPointsRetries|



#### **DistributionPointUpdateSchedule**








|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **EnableBinaryDeltaReplication**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

ForceWildcardHandling processes wildcard characters and may lead to unexpected behavior (not recommended). Can't combine with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of IDs of OS images.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **InputObject**

Specifies a CMOperatingSystemImage object. To obtain a CMOperatingSystemImage object, use the Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **MulticastAllow**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MulticastEncrypt**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MulticastTransferOnly**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specifies the name of an OS image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Specifies the new name of an OS image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

Specifies the network path to the OS image source .wim file.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|false   |named   |False        |PackageSourcePath|



#### **PersistContentInCache**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PrestageBehavior**





Valid Values:

* ManualCopy
* DownloadDelta
* OnDemand






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[PrestageBehavior]`|false   |named   |False        |



#### **Priority**

Specifies a change for the priority of the deployment type. Valid values are: Increase and Decrease.



Valid Values:

* High
* Medium
* Low






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[Priority]`|false   |named   |False        |



#### **Reload**

Applies to version 2006 and later. If you change the image properties using an external tool, use this option to reload the information in the site database.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[Switch]`|false   |named   |False        |ReloadImage|



#### **SendToPreferredDistributionPoint**








|Type       |Required|Position|PipelineInput|Aliases                          |
|-----------|--------|--------|-------------|---------------------------------|
|`[Boolean]`|false   |named   |False        |SendToPreferredDistributionPoints|



#### **Version**

Specifies the version of the OS image.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMOperatingSystemImage [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetryCount <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-ForceWildcardHandling] -Id <String> [-MulticastAllow <Boolean>] [-MulticastEncrypt <Boolean>] [-MulticastTransferOnly <Boolean>] [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-Priority {High | Medium | Low}] [-Reload] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMOperatingSystemImage [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetryCount <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-MulticastAllow <Boolean>] [-MulticastEncrypt <Boolean>] [-MulticastTransferOnly <Boolean>] [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-Priority {High | Medium | Low}] [-Reload] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMOperatingSystemImage [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetryCount <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-ForceWildcardHandling] [-MulticastAllow <Boolean>] [-MulticastEncrypt <Boolean>] [-MulticastTransferOnly <Boolean>] -Name <String> [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-Priority {High | Medium | Low}] [-Reload] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
