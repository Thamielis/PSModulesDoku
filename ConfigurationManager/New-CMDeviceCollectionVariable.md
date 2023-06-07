New-CMDeviceCollectionVariable
------------------------------




### Synopsis
Create a device collection variable.



---


### Description

Use this cmdlet to create a device collection variable. You can use a device collection variable to define custom task sequence variables and their associated values to be used by the devices in a collection. Task sequence variables are a set of name and value pairs that provide a mechanism to configure and customize the steps of a task sequence when the task sequence is deployed to a specific collection.



Default collections can't have variables. Any collection that you target should have an ID that starts with the site code, not `SMS`.



For more information, see How to set task sequence variables (/mem/configmgr/osd/understand/using-task-sequence-variables#bkmk_set).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeviceCollectionVariable](Get-CMDeviceCollectionVariable)



* [Remove-CMDeviceCollectionVariable](Remove-CMDeviceCollectionVariable)



* [Set-CMDeviceCollectionVariable](Set-CMDeviceCollectionVariable)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [New-CMDeviceVariable](New-CMDeviceVariable)



* [How to set task sequence variables](How to set task sequence variables)





---


### Examples
#### Example 1: Create a device collection variable
```PowerShell
$Collection = Get-CMCollection -Name "Device"
New-CMDeviceCollectionVariable -Collection $Collection -VariableName "testTS" -Value "test001"
```



---


### Parameters
#### **CollectionId**

Specify the ID of a device collection on which to create the variable. This value is the CollectionID property, for example, `XYZ00012`. Since you can't set variables on default collections, this value starts with the site code, not `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specify the name of a device collection on which to create the variable.






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



#### **InputObject**

Specify a device collection object on which to create the variable. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **IsMask**

Set this parameter to `$true` to indicate that the variable value is hidden. Masked values aren't displayed in the Configuration Manager console, the Value property on the WMI class SMS_CollectionVariable , or the task sequence log file. The task sequence can still use the variable.


You can't unmask a variable once it's hidden. If you mask a variable's value, but then don't want it masked, you need to delete and recreate the variable.


If you don't include this parameter, values aren't masked by default.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Value**

Specify a value for the collection variable.






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[String]`|false   |named   |False        |VariableValue|



#### **VariableName**

Specify a name for the collection variable to create.






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
* IResultObject[]#SMS_CollectionSettings


* IResultObject#SMS_CollectionSettings






---


### Notes
For more information on this return object and its properties, see SMS_CollectionSettings server WMI class (/mem/configmgr/develop/reference/core/clients/collections/sms_collectionsettings-server-wmi-class).



---


### Syntax
```PowerShell
New-CMDeviceCollectionVariable -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsMask <Boolean>] [-Value <String>] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMDeviceCollectionVariable -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsMask <Boolean>] [-Value <String>] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMDeviceCollectionVariable [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsMask <Boolean>] [-Value <String>] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
