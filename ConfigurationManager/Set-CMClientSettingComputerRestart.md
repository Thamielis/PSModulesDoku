Set-CMClientSettingComputerRestart
----------------------------------




### Synopsis
Set client settings for computer restart.



---


### Description

Set client settings for computer restart. For more information, see device restart notifications (/mem/configmgr/core/clients/deploy/device-restart-notifications).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Device restart notifications](Device restart notifications)





---


### Examples
#### Example 1
```PowerShell
{{ Add example code here }}
```



---


### Parameters
#### **CountdownMins**








|Type     |Required|Position|PipelineInput|Aliases                                                                                   |
|---------|--------|--------|-------------|------------------------------------------------------------------------------------------|
|`[Int32]`|false   |named   |False        |RebootLogoffNotificationCountdownDurationMinutes<br/>RebootLogoffNotificationCountdownMins|



#### **DefaultSetting**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FinalWindowMins**








|Type     |Required|Position|PipelineInput|Aliases                                                                               |
|---------|--------|--------|-------------|--------------------------------------------------------------------------------------|
|`[Int32]`|false   |named   |False        |RebootLogoffNotificationFinalWindowMinutes<br/>RebootLogoffNotificationFinalWindowMins|



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



#### **NoRebootEnforcement**

Applies to version 2006 and later. Configure the client setting Configuration Manager can force a device to restart to prevent devices from automatically restarting when a deployment requires it. By default, Configuration Manager can still force devices to restart.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ReplaceToastNotificationWithDialog**

Specify whether to replace toast notifications with a more intrusive dialog window when a deployment requires a restart. It's an optional parameter and false by default.






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
Set-CMClientSettingComputerRestart [-CountdownMins <Int32>] -DefaultSetting [-DisableWildcardHandling] [-FinalWindowMins <Int32>] [-ForceWildcardHandling] [-NoRebootEnforcement <Boolean>] [-PassThru] [-ReplaceToastNotificationWithDialog <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingComputerRestart [-CountdownMins <Int32>] [-DisableWildcardHandling] [-FinalWindowMins <Int32>] [-ForceWildcardHandling] -InputObject <IResultObject> [-NoRebootEnforcement <Boolean>] [-PassThru] [-ReplaceToastNotificationWithDialog <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingComputerRestart [-CountdownMins <Int32>] [-DisableWildcardHandling] [-FinalWindowMins <Int32>] [-ForceWildcardHandling] -Name <String> [-NoRebootEnforcement <Boolean>] [-PassThru] [-ReplaceToastNotificationWithDialog <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
