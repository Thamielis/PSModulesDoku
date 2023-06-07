New-CMDeviceVariable
--------------------




### Synopsis
Creates a device variable for a Configuration Manager device.



---


### Description

The New-CMDeviceVariable cmdlet creates a device variable for a Configuration Manager device.



Individual devices have device variables. Task sequence processing uses device variables.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeviceVariable](Get-CMDeviceVariable)



* [Remove-CMDeviceVariable](Remove-CMDeviceVariable)



* [Set-CMDeviceVariable](Set-CMDeviceVariable)



* [Get-CMDevice](Get-CMDevice)





---


### Examples
#### Example 1: Create a device variable
```PowerShell
PS XYZ:\> New-CMDeviceVariable -DeviceName "gateway-server.contoso.com" -VariableName "ServerIPAddress" -VariableValue "192.168.1.1" -IsMask 0
```
This command creates a device variable for the device gateway-server.contoso.com. The variable is named ServerIPAddress and the value is set to 192.168.1.1. Setting the IsMask parameter to 0 ensures that the variable is displayed in the Configuration Manager console.


---


### Parameters
#### **DeviceId**

Specifies a device ID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Device |



#### **IsMask**

Indicates whether the variable value is displayed in the Configuration Manager console.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **VariableName**

Specifies the name of the device variable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **VariableValue**

Specifies the value of the variable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* IResultObject#SMS_MachineSettings






---


### Notes




---


### Syntax
```PowerShell
New-CMDeviceVariable -DeviceId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsMask <Boolean>] -VariableName <String> [-VariableValue <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMDeviceVariable -DeviceName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsMask <Boolean>] -VariableName <String> [-VariableValue <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMDeviceVariable [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsMask <Boolean>] -VariableName <String> [-VariableValue <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
