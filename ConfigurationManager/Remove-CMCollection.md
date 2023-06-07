Remove-CMCollection
-------------------




### Synopsis
Remove a device or user collection.



---


### Description

Use this cmdlet to remove a device or user collection.



You can't remove default collections. Any collection that you target should have an ID that starts with the site code, not `SMS`.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMCollection](Copy-CMCollection)



* [Export-CMCollection](Export-CMCollection)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMCollectionMember](Get-CMCollectionMember)



* [Get-CMCollectionSetting](Get-CMCollectionSetting)



* [Import-CMCollection](Import-CMCollection)



* [Invoke-CMCollectionUpdate](Invoke-CMCollectionUpdate)



* [New-CMCollection](New-CMCollection)



* [Set-CMCollection](Set-CMCollection)



* [Remove-CMDeviceCollectionVariable](Remove-CMDeviceCollectionVariable)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Remove a collection by name
```PowerShell
Remove-CMCollection -Name "testUser" -Force
```

#### Example 2: Get a collection object and remove it
```PowerShell
Get-CMCollection -Name "testUser" | Remove-CMCollection
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of a collection to remove. This value is the CollectionID property, for example, `XYZ00012`. You can't remove default collections, so this value starts with the site code, not `SMS`.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CollectionId|



#### **InputObject**

Specify a collection object to remove. To get this object, use the Get-CMCollection (Get-CMCollection.md), [Get-CMDeviceCollection](Get-CMDeviceCollection.md), or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a collection to remove.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMCollection [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollection [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollection [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
