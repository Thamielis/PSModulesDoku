Set-CMClientSettingEndpointProtection
-------------------------------------




### Synopsis
Sets a client setting endpoint protection.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



---


### Parameters
#### **DefaultSetting**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableFirstSignatureUpdate**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Enable**








|Type       |Required|Position|PipelineInput|Aliases                 |
|-----------|--------|--------|-------------|------------------------|
|`[Boolean]`|false   |named   |False        |EnableEndpointProtection|



#### **ForceRebootHr**








|Type     |Required|Position|PipelineInput|Aliases                               |
|---------|--------|--------|-------------|--------------------------------------|
|`[Int32]`|false   |named   |False        |ForceRebootPeriod<br/>ForceRebootHours|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **InstallEndpointProtectionClient**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **OverrideMaintenanceWindow**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PersistInstallation**








|Type       |Required|Position|PipelineInput|Aliases                                   |
|-----------|--------|--------|-------------|------------------------------------------|
|`[Boolean]`|false   |named   |False        |CommitEndpointProtectionClientInstallation|



#### **RemoveThirdParty**

The parameter 'RemoveThirdParty' has been deprecated and may be removed in a future release.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SuppressReboot**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
Set-CMClientSettingEndpointProtection -DefaultSetting [-DisableFirstSignatureUpdate <Boolean>] [-DisableWildcardHandling] [-Enable <Boolean>] [-ForceRebootHr <Int32>] [-ForceWildcardHandling] [-InstallEndpointProtectionClient <Boolean>] [-OverrideMaintenanceWindow <Boolean>] [-PassThru] [-PersistInstallation <Boolean>] [-RemoveThirdParty <Boolean>] [-SuppressReboot <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingEndpointProtection [-DisableFirstSignatureUpdate <Boolean>] [-DisableWildcardHandling] [-Enable <Boolean>] [-ForceRebootHr <Int32>] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallEndpointProtectionClient <Boolean>] [-OverrideMaintenanceWindow <Boolean>] [-PassThru] [-PersistInstallation <Boolean>] [-RemoveThirdParty <Boolean>] [-SuppressReboot <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingEndpointProtection [-DisableFirstSignatureUpdate <Boolean>] [-DisableWildcardHandling] [-Enable <Boolean>] [-ForceRebootHr <Int32>] [-ForceWildcardHandling] [-InstallEndpointProtectionClient <Boolean>] -Name <String> [-OverrideMaintenanceWindow <Boolean>] [-PassThru] [-PersistInstallation <Boolean>] [-RemoveThirdParty <Boolean>] [-SuppressReboot <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
