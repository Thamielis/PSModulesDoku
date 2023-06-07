Set-CMWindows10EditionUpgrade
-----------------------------




### Synopsis
Configure a Windows 10 edition upgrade policy.



---


### Description

Configure a Windows 10 edition upgrade policy.



---


### Related Links
* [Get-CMWindowsEditionUpgradeConfigurationItem](Get-CMWindowsEditionUpgradeConfigurationItem)



* [New-CMWindows10EditionUpgrade](New-CMWindows10EditionUpgrade)



* [Remove-CMWindows10EditionUpgrade](Remove-CMWindows10EditionUpgrade)



* [Upgrade Windows devices to a new edition with Configuration Manager](Upgrade Windows devices to a new edition with Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
$win10UpgradePolicyId = 16777523

$newDescription = "update description for the edition upgrade policy"

Set-CMWindows10EditionUpgrade -Id $win10UpgradePolicyId -Description $newDescription
```



---


### Parameters
#### **Description**

Specify a new description for the edition upgrade policy.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



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



#### **Id**

Specify the ID of the Windows 10 edition upgrade policy to configure. This ID is the CI ID of the policy, for example: `552481`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify an object for the Windows 10 edition upgrade policy to configure. To get this object, use the Get-CMWindowsEditionUpgradeConfigurationItem (Get-CMWindowsEditionUpgradeConfigurationItem.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                      |
|-----------------|--------|--------|--------------|-----------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Windows10EditionUpgradePolicy|



#### **Name**

Specify the name of the Windows 10 edition upgrade policy to configure.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **NewName**

Use this parameter to rename the edition upgrade policy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
* IResultObject#SMS_ConfigurationPolicy






---


### Notes




---


### Syntax
```PowerShell
Set-CMWindows10EditionUpgrade [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMWindows10EditionUpgrade [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMWindows10EditionUpgrade [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
