Set-CMClientSettingPowerManagement
----------------------------------




### Synopsis
Sets a client setting power management.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example
```PowerShell
Set-CMClientSettingPowerManagement -Name "test settings" -AllowUserToOptOutFromPowerPlan $true -EnableWakeupProxy $true -NetworkWakeupOption Enabled -WakeupProxyPort 25511 -WakeOnLanPort 10 -FirewallExceptionForWakeupProxy None
```



---


### Parameters
#### **AllowUserToOptOutFromPowerPlan**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DefaultSetting**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Enable**








|Type       |Required|Position|PipelineInput|Aliases              |
|-----------|--------|--------|-------------|---------------------|
|`[Boolean]`|false   |named   |False        |EnablePowerManagement|



#### **EnableWakeupProxy**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **FirewallExceptionForWakeupProxy**





Valid Values:

* None
* Public
* Private
* Domain






|Type                                 |Required|Position|PipelineInput|Aliases                                |
|-------------------------------------|--------|--------|-------------|---------------------------------------|
|`[WakeUpProxyFirewallExceptionTypes]`|false   |named   |False        |WindowsFirewallExceptionsForWakeupProxy|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NetworkWakeupOption**

Use this parameter to enable or disable the client setting, Allow network wake-up .



Valid Values:

* NotConfigured
* Enabled
* Disabled






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[NetworkWakeupType]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **WakeOnLanPort**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **WakeupProxyDirectAccessPrefix**








|Type      |Required|Position|PipelineInput|Aliases                                               |
|----------|--------|--------|-------------|------------------------------------------------------|
|`[String]`|false   |named   |False        |IPv6PrefixesForDirectAccessOrInterveningNetworkDevices|



#### **WakeupProxyPort**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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
Set-CMClientSettingPowerManagement [-AllowUserToOptOutFromPowerPlan <Boolean>] -DefaultSetting [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableWakeupProxy <Boolean>] [-FirewallExceptionForWakeupProxy {None | Public | Private | Domain}] [-ForceWildcardHandling] [-NetworkWakeupOption {NotConfigured | Enabled | Disabled}] [-PassThru] [-WakeOnLanPort <Int32>] [-WakeupProxyDirectAccessPrefix <String>] [-WakeupProxyPort <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingPowerManagement [-AllowUserToOptOutFromPowerPlan <Boolean>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableWakeupProxy <Boolean>] [-FirewallExceptionForWakeupProxy {None | Public | Private | Domain}] [-ForceWildcardHandling] -InputObject <IResultObject> [-NetworkWakeupOption {NotConfigured | Enabled | Disabled}] [-PassThru] [-WakeOnLanPort <Int32>] [-WakeupProxyDirectAccessPrefix <String>] [-WakeupProxyPort <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingPowerManagement [-AllowUserToOptOutFromPowerPlan <Boolean>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableWakeupProxy <Boolean>] [-FirewallExceptionForWakeupProxy {None | Public | Private | Domain}] [-ForceWildcardHandling] -Name <String> [-NetworkWakeupOption {NotConfigured | Enabled | Disabled}] [-PassThru] [-WakeOnLanPort <Int32>] [-WakeupProxyDirectAccessPrefix <String>] [-WakeupProxyPort <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
