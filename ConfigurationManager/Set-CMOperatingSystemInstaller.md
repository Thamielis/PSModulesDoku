Set-CMOperatingSystemInstaller
------------------------------




### Synopsis
Changes configuration settings of OS upgrade packages.



---


### Description

The Set-CMOperatingSystemInstaller cmdlet changes configuration settings of one or more OS upgrade packages in Configuration Manager. An OS upgrade package contains all the files that Configuration Manager needs to install a Windows OS on a reference computer.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMOperatingSystemInstaller](Get-CMOperatingSystemInstaller)



* [New-CMOperatingSystemInstaller](New-CMOperatingSystemInstaller)



* [Remove-CMOperatingSystemInstaller](Remove-CMOperatingSystemInstaller)





---


### Examples
#### Example 1: Change settings for an OS upgrade package by using a name
```PowerShell
Set-CMOperatingSystemInstaller -Name "Win8x64" -NewName "OsiWin8x64" -Version "I20B" -Description "Dept02 Sys Install" -Path "\\Win2k3X64contoso\Public\OSD\win8x64"
```

#### Example 2: Add an OS upgrade package to a security scope by using a name
```PowerShell
Set-CMOperatingSystemInstaller -SecurityScopeAction AddMembership -SecurityScopeName "SecScope02" -Name "InstPkg01"
```

#### Example 3: Remove an OS upgrade package from a security scope
```PowerShell
Set-CMOperatingSystemInstaller -SecurityScopeAction RemoveMembership -SecurityScopeName "SecScope02" -Name "InstPkg01"
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

Specifies a description for the OS upgrade package.






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

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of IDs of OS upgrade packages.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **InputObject**

Specifies a CMOperatingSystemInstaller object. To obtain a CMOperatingSystemInstaller object, use the Get-CMOperatingSystemInstaller (Get-CMOperatingSystemInstaller.md)cmdlet.






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

Specifies the name of an OS upgrade package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Specifies the new name of an OS upgrade package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

Specifies the network path to the installation source files of an OS upgrade package.






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

Specifies the version of an OS upgrade package.






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
Set-CMOperatingSystemInstaller [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetryCount <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-ForceWildcardHandling] -Id <String> [-MulticastAllow <Boolean>] [-MulticastEncrypt <Boolean>] [-MulticastTransferOnly <Boolean>] [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-Priority {High | Medium | Low}] [-Reload] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMOperatingSystemInstaller [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetryCount <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-MulticastAllow <Boolean>] [-MulticastEncrypt <Boolean>] [-MulticastTransferOnly <Boolean>] [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-Priority {High | Medium | Low}] [-Reload] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMOperatingSystemInstaller [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetryCount <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-ForceWildcardHandling] [-MulticastAllow <Boolean>] [-MulticastEncrypt <Boolean>] [-MulticastTransferOnly <Boolean>] -Name <String> [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-Priority {High | Medium | Low}] [-Reload] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
