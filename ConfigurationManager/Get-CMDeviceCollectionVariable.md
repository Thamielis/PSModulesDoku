Get-CMDeviceCollectionVariable
------------------------------




### Synopsis
Get a device collection variable.



---


### Description

Use this cmdlet to get the task sequence variables on a device collection. Default collections can't have variables. Any collection that you target should have an ID that starts with the site code, not `SMS`.



For more information, see How to set task sequence variables (/mem/configmgr/osd/understand/using-task-sequence-variables#bkmk_set).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDeviceCollectionVariable](New-CMDeviceCollectionVariable)



* [Remove-CMDeviceCollectionVariable](Remove-CMDeviceCollectionVariable)



* [Set-CMDeviceCollectionVariable](Set-CMDeviceCollectionVariable)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMDeviceVariable](Get-CMDeviceVariable)



* [How to set task sequence variables](How to set task sequence variables)





---


### Examples
#### Example 1: Get a device collection variable by name
```PowerShell
Get-CMDeviceCollectionVariable -CollectionName "DeviceCollection02" -VariableName "testTS"
```

#### Example 2: Get all unmasked variables for a collection
```PowerShell
Get-CMDeviceCollectionVariable -CollectionName "IT servers" | Where-Object { -not $_.IsMasked } | Select-Object Name, Value
```



---


### Parameters
#### **Collection**

Specify a device collection object to get its variables. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **CollectionId**

Specify the ID of a device collection to get its variables. This value is the CollectionID property, for example, `XYZ00012`. Since you can't set variables on default collections, this value starts with the site code, not `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specify the name of a device collection to get its variables.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **VariableName**

Specify the name of a collection variable to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_CollectionVariable


* IResultObject#SMS_CollectionVariable






---


### Notes
For more information on this return object and its properties, see SMS_CollectionVariable server WMI class (/mem/configmgr/develop/reference/osd/sms_collectionvariable-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMDeviceCollectionVariable -Collection <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-VariableName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionVariable -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-VariableName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionVariable -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-VariableName <String>] [<CommonParameters>]
```
