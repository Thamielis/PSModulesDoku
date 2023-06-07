Remove-CMDeviceVariable
-----------------------




### Synopsis
Removes a variable defined for a Configuration Manager device.



---


### Description

The Remove-CMDeviceVariable cmdlet removes a variable defined for a Configuration Manager device.



Individual devices have device variables. Task sequence processing uses device variables.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeviceVariable](Get-CMDeviceVariable)



* [New-CMDeviceVariable](New-CMDeviceVariable)



* [Set-CMDeviceVariable](Set-CMDeviceVariable)





---


### Examples
#### Example 1: Remove a device variable
```PowerShell
PS XYZ:\> Remove-CMDeviceVariable -DeviceName "gateway-server.contoso.com" -VariableName "ServerIPAddress"
```
This command removes the device variable ServerIPAddress from the device gateway-server.contoso.com.


---


### Parameters
#### **Device**

Specifies a CMDevice object. To obtain a CMDevice object, use the Get-CMDevice (Get-CMDevice.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |named   |True (ByValue)|InputObject|



#### **DeviceName**

Specifies a device name. You can specify a NetBIOS name or a fully qualified domain name (FQDN).






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



#### **ResourceId**

Specifies a Systems Management Server (SMS) ID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **VariableName**

Specifies the name of the device variable that this cmdlet removes.






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
Remove-CMDeviceVariable -Device <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeviceVariable -DeviceName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeviceVariable [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -ResourceId <String> -VariableName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
