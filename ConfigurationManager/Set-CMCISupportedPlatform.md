Set-CMCISupportedPlatform
-------------------------




### Synopsis
Configure the supported platforms for a configuration item.



---


### Description

Use this cmdlet to configure the supported platforms for a configuration item. For more information, see Create configuration items in Configuration Manager (/mem/configmgr/compliance/deploy-use/create-configuration-items).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSupportedPlatform](Get-CMSupportedPlatform)



* [Get-CMConfigurationItem](Get-CMConfigurationItem)



* [Create configuration items in Configuration Manager](Create configuration items in Configuration Manager)





---


### Examples
#### Example 1: Set platform for configuration item
```PowerShell
$mac_ci = Get-CMConfigurationItem -Name "Mac CI"

$mac_platform1 = Get-CMSupportedPlatform -Name "Mac OS X 10.8"
$mac_platform2 = Get-CMSupportedPlatform -Name "Mac OS X 10.9"
$mac_platforms = $mac_platform1,$mac_platform2

$mac_platform3 = Get-CMSupportedPlatform -Name "Mac OS X 10.7"
$mac_platform4 = Get-CMSupportedPlatform -Name "Mac OS X 10.6"
$mac_platforms2 = $mac_platform3,$mac_platform4

Set-CMCISupportedPlatform -InputObject $mac_ci -AddSupportedPlatform $mac_platforms -RemoveSupportedPlatform $mac_platforms2
```



---


### Parameters
#### **AddSupportedPlatform**

Specify one or more supported platform objects to add to the configuration item. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases              |
|-------------------|--------|--------|-------------|---------------------|
|`[IResultObject[]]`|false   |named   |False        |AddSupportedPlatforms|



#### **DefineVersionManually**

Add this parameter to manually specify the OS version.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a configuration item object to add the supported platforms. To get this object, use the Get-CMConfigurationItem (Get-CMConfigurationItem.md)cmdlet.






|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[PSObject]`|true    |0       |True (ByValue)|



#### **Is64BitRequired**

Set this parameter to $true to require 64-bit OS platforms.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveSupportedPlatform**

Specify one or more supported platform objects to remove from the configuration item. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                 |
|-------------------|--------|--------|-------------|------------------------|
|`[IResultObject[]]`|false   |named   |False        |RemoveSupportedPlatforms|



#### **ServicePackMajor**

If you use the DefineVersionManually parameter, specify the service pack major version as an integer value.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ServicePackMinor**

If you use the DefineVersionManually parameter, specify the service pack minor version as an integer value.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **VersionBuild**

If you use the DefineVersionManually parameter, specify the build number as an integer value.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **VersionMajor**

If you use the DefineVersionManually parameter, specify the major version as an integer value.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **VersionMinor**

If you use the DefineVersionManually parameter, specify the minor version as an integer value.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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
System.Management.Automation.PSObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMCISupportedPlatform [-InputObject] <PSObject> [-AddSupportedPlatform <IResultObject[]>] [-DefineVersionManually] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Is64BitRequired <Boolean>] [-PassThru] [-RemoveSupportedPlatform <IResultObject[]>] [-ServicePackMajor <Int32>] [-ServicePackMinor <Int32>] [-VersionBuild <Int32>] [-VersionMajor <Int32>] [-VersionMinor <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
