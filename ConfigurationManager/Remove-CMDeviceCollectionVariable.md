Remove-CMDeviceCollectionVariable
---------------------------------




### Synopsis
Remove a device collection variable.



---


### Description

Use this cmdlet to remove a device collection variable. Default collections can't have variables. Any collection that you target should have an ID that starts with the site code, not `SMS`.



For more information, see How to set task sequence variables (/mem/configmgr/osd/understand/using-task-sequence-variables#bkmk_set).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeviceCollectionVariable](Get-CMDeviceCollectionVariable)



* [New-CMDeviceCollectionVariable](New-CMDeviceCollectionVariable)



* [Set-CMDeviceCollectionVariable](Set-CMDeviceCollectionVariable)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Remove-CMDeviceVariable](Remove-CMDeviceVariable)



* [How to set task sequence variables](How to set task sequence variables)





---


### Examples
#### Example 1: Remove a device collection variable
```PowerShell
$Collection = Get-CMCollection -Name "Device"
Remove-CMDeviceCollectionVariable -Collection $Collection -VariableName "testTS" -Force
```

#### Example 2: Remove all variables from a device collection
```PowerShell
$collName = "IT servers"
$vars = Get-CMDeviceCollectionVariable -CollectionName $collName

foreach ( $var in $vars ) {
  Remove-CMDeviceCollectionVariable -CollectionName $collName -VariableName $var -Force
}
```
Since the VariableName parameter doesn't allow wildcards, use this process if you need to quickly clear all variables from a device collection.


---


### Parameters
#### **Collection**

Specify a device collection object to remove its variables. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **CollectionId**

Specify the ID of a device collection to remove its variables. This value is the CollectionID property, for example, `XYZ00012`. Since you can't set variables on default collections, this value starts with the site code, not `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specify the name of a device collection to remove its variables.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **VariableName**

Specify the name of a collection variable to remove. This parameter doesn't accept wildcard characters.






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
Remove-CMDeviceCollectionVariable -Collection <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeviceCollectionVariable -CollectionId <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeviceCollectionVariable -CollectionName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
