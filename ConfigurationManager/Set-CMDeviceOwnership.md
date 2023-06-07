Set-CMDeviceOwnership
---------------------




### Synopsis
Configures ownership type for a device.



---


### Description

The Set-CMDeviceOwnership cmdlet configures ownership type for a modern device. For a personal device, the information gathered is limited, and personal information is not removed during a wipe operation. For a company-owned device, additional information can be gathered and deleted during a wipe operation.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Invoke-CMDeviceWipe](Invoke-CMDeviceWipe)



* [Get-CMDevice](Get-CMDevice)





---


### Examples
#### Example 1: Identify a device as a company asset
```PowerShell
PS XYZ:\> Set-CMDeviceOwnership -DeviceId "209846738" -OwnershipType Company
```
This command identifies the specified device as a company asset.


---


### Parameters
#### **DeviceId**

Specifies an array of device IDs.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |ResourceId|



#### **DeviceName**

Specifies an array of device names.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



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

Specifies a CMDevice object. To obtain a CMDevice object, use the Get-CMDevice (Get-CMDevice.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **OwnershipType**

Specifies the type of ownership for a device. The acceptable values for this parameter are:


* Company. The device is a company asset. - Personal. The device is not a company asset.



Valid Values:

* Company
* Personal






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[DeviceOwnershipType]`|true    |named   |False        |



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
Set-CMDeviceOwnership -DeviceId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -OwnershipType {Company | Personal} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeviceOwnership -DeviceName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -OwnershipType {Company | Personal} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeviceOwnership [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -OwnershipType {Company | Personal} [-Confirm] [-WhatIf] [<CommonParameters>]
```
