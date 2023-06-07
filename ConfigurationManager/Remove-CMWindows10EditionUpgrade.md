Remove-CMWindows10EditionUpgrade
--------------------------------




### Synopsis
Remove a Windows 10 edition upgrade policy.



---


### Description

Remove a Windows 10 edition upgrade policy. When you remove this policy, clients in the target collection won't upgrade to the new Windows 10 edition.



---


### Related Links
* [Get-CMWindowsEditionUpgradeConfigurationItem](Get-CMWindowsEditionUpgradeConfigurationItem)



* [New-CMWindows10EditionUpgrade](New-CMWindows10EditionUpgrade)



* [Set-CMWindows10EditionUpgrade](Set-CMWindows10EditionUpgrade)



* [Upgrade Windows devices to a new edition with Configuration Manager](Upgrade Windows devices to a new edition with Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Remove-CMWindows10EditionUpgrade -Id 16777523 -Force
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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



#### **Id**

Specify the ID of the Windows 10 edition upgrade policy to remove. This ID is the CI ID of the policy, for example: `552481`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify an object for the Windows 10 edition upgrade policy to remove. To get this object, use the Get-CMWindowsEditionUpgradeConfigurationItem (Get-CMWindowsEditionUpgradeConfigurationItem.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specify the name of the Windows 10 edition upgrade policy to remove.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



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
Remove-CMWindows10EditionUpgrade [-Id] <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMWindows10EditionUpgrade [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMWindows10EditionUpgrade [-Name] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
