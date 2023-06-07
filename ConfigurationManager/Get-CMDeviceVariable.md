Get-CMDeviceVariable
--------------------




### Synopsis
Gets device variables of a Configuration Manager device.



---


### Description

The Get-CMDeviceVariable cmdlet gets device variables of a Configuration Manager device.



Individual devices have device variables. Task sequence processing uses device variables.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDeviceVariable](New-CMDeviceVariable)



* [Remove-CMDeviceVariable](Remove-CMDeviceVariable)



* [Set-CMDeviceVariable](Set-CMDeviceVariable)



* [Get-CMDevice](Get-CMDevice)





---


### Examples
#### Example 1: Get a variable value by using its name
```PowerShell
PS XYZ:\> Get-CMDeviceVariable -DeviceName "Computer073" -VariableName "HostDrive"
```
This command gets the value of the variable named HostDrive for the specified computer.


---


### Parameters
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



#### **ResourceId**

Specifies a Systems Management Server (SMS) ID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **VariableName**

Specifies the name of the device variable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_MachineSettings


* IResultObject#SMS_MachineSettings






---


### Notes




---


### Syntax
```PowerShell
Get-CMDeviceVariable -DeviceName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-VariableName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDeviceVariable [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-VariableName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDeviceVariable [-DisableWildcardHandling] [-ForceWildcardHandling] -ResourceId <String> [-VariableName <String>] [<CommonParameters>]
```
