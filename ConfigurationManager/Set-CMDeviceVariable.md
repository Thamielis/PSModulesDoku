Set-CMDeviceVariable
--------------------




### Synopsis
Modify a device variable.



---


### Description

Use this cmdlet to modify a variable on a Configuration Manager device.



Individual devices have device variables. Task sequence processing uses device variables. For more information, see Collection and device variables (/mem/configmgr/osd/understand/using-task-sequence-variables#bkmk_set-coll-var).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeviceVariable](Get-CMDeviceVariable)



* [New-CMDeviceVariable](New-CMDeviceVariable)



* [Remove-CMDeviceVariable](Remove-CMDeviceVariable)





---


### Examples
#### Example 1: Modify a device variable
```PowerShell
Set-CMDeviceVariable -DeviceName "server01" -VariableName "ServerIPAddress" -NewVariableValue "192.168.100.10"
```



---


### Parameters
#### **DeviceName**

Specify a device name. You can specify a NetBIOS name or a fully qualified domain name (FQDN).






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

Specify a device object on which to set the variable. To get this object, use the Get-CMDevice (Get-CMDevice.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Device |



#### **IsMask**

Set this parameter to `$true` to hide the value in the Configuration Manager console.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **NewVariableName**

Specify a new name for the variable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NewVariableValue**

Specify a new value for the variable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ResourceId**

Specify the resource ID of the device.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **VariableName**

Specify the name of the device variable.


Starting in version 2111, this parameter is case insensitive.






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
Set-CMDeviceVariable -DeviceName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsMask <Boolean>] [-NewVariableName <String>] [-NewVariableValue <String>] [-PassThru] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeviceVariable [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsMask <Boolean>] [-NewVariableName <String>] [-NewVariableValue <String>] [-PassThru] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeviceVariable [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsMask <Boolean>] [-NewVariableName <String>] [-NewVariableValue <String>] [-PassThru] -ResourceId <String> -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
