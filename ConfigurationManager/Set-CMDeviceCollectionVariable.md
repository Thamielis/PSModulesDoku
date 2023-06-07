Set-CMDeviceCollectionVariable
------------------------------




### Synopsis
Configure a device collection variable.



---


### Description

Use this cmdlet to change a device collection variable.



Default collections can't have variables. Any collection that you target should have an ID that starts with the site code, not `SMS`.



For more information, see How to set task sequence variables (/mem/configmgr/osd/understand/using-task-sequence-variables#bkmk_set).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeviceCollectionVariable](Get-CMDeviceCollectionVariable)



* [New-CMDeviceCollectionVariable](New-CMDeviceCollectionVariable)



* [Remove-CMDeviceCollectionVariable](Remove-CMDeviceCollectionVariable)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Set-CMDeviceVariable](Set-CMDeviceVariable)



* [How to set task sequence variables](How to set task sequence variables)





---


### Examples
#### Example 1: Change a variable name
```PowerShell
$Collection = Get-CMCollection -Name "Device"
Set-CMDeviceCollectionVariable -Collection $Collection -VariableName "testTS" -NewVariableName "NewVariable"
```

#### Example 2: Change a variable value
```PowerShell
Set-CMDeviceCollectionVariable -CollectionName "Device" -VariableName "testTS" -NewVariableValue 12
```



---


### Parameters
#### **CollectionId**

Specify the ID of a device collection to configure a variable. This value is the CollectionID property, for example, `XYZ00012`. Since you can't set variables on default collections, this value starts with the site code, not `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specify the name of a device collection to configure a variable.






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

Specify a device collection object to configure a variable. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **IsMask**

Set this parameter to `$true` to indicate that the variable value is hidden. Masked values aren't displayed in the Configuration Manager console, the Value property on the WMI class SMS_CollectionVariable , or the task sequence log file. The task sequence can still use the variable.


You can't unmask a variable once it's hidden. If you mask a variable's value, but then don't want it masked, you need to delete and recreate the variable.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **NewVariableName**

Specify a new name for the collection variable. Use this parameter to rename the variable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NewVariableValue**

Specify a new value for the collection variable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **VariableName**

Specify the name of the collection variable to change.






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
To set the variable priority, use the Set-CMCollection (Set-CMCollection.md) cmdlet with the **VariablePriority** parameter. To view the current variable priority, use the [Get-CMCollectionSetting](Get-CMCollectionSetting.md)cmdlet.



---


### Syntax
```PowerShell
Set-CMDeviceCollectionVariable -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsMask <Boolean>] [-NewVariableName <String>] [-NewVariableValue <String>] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeviceCollectionVariable -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsMask <Boolean>] [-NewVariableName <String>] [-NewVariableValue <String>] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeviceCollectionVariable [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsMask <Boolean>] [-NewVariableName <String>] [-NewVariableValue <String>] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
