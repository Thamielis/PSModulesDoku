Invoke-CMDeviceRetire
---------------------




### Synopsis
Retires devices.



---


### Description

The Invoke-CMDeviceRetire cmdlet retires one or more devices. A retired device is no longer active in Configuration Manager. It does not receive new policies or policy updates. Retired devices remain listed until a maintenance task removes them.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDevice](Get-CMDevice)





---


### Examples
#### Example 1: Retire a named device
```PowerShell
PS XYZ:\>Invoke-CMDeviceRetire -DeviceName "Computer073"
```
This command retires the computer named Computer073.


---


### Parameters
#### **Cancel**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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








|Type     |Required|Position|PipelineInput|Aliases                |
|---------|--------|--------|-------------|-----------------------|
|`[Int32]`|true    |named   |False        |DeviceId<br/>ResourceId|



#### **InputObject**

Specifies a CMDevice object. To obtain a CMDevice object, use the Get-CMDevice (Get-CMDevice.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Device |



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |DeviceName|



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
Invoke-CMDeviceRetire [-Cancel] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMDeviceRetire [-Cancel] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMDeviceRetire [-Cancel] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
