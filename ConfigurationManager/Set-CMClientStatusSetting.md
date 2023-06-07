Set-CMClientStatusSetting
-------------------------




### Synopsis
Modifies client status settings.



---


### Description

The Set-CMClientStatusSetting cmdlet modifies client status settings. These settings determine the data collection intervals for individual client monitoring activities in Configuration Manager.



For more information about client settings, see About Client Settings in Configuration Manager (/mem/configmgr/core/clients/deploy/about-client-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [About Client Settings in Configuration Manager](About Client Settings in Configuration Manager)



* [Get-CMClientStatusSetting](Get-CMClientStatusSetting)



* [Update-CMClientStatus](Update-CMClientStatus)



* [Get-CMClientStatusUpdateSchedule](Get-CMClientStatusUpdateSchedule)





---


### Examples
#### Example 1: Modify all client status settings
```PowerShell
PS XYZ:\> Set-CMClientStatusSetting -ClientPolicyDayInterval 2 -HeartbeatDiscoveryDayInterval 3 -HardwareInventoryDayInterval 4 -SoftwareInventoryDayInterval 5 -StatusMessageDayInterval 6 -HistoryCleanupDayInterval 7
```
This command modifies all client status settings.
#### Example 2: Modify the Client Policy setting
```PowerShell
PS XYZ:\> Set-CMClientStatusSetting -ClientPolicyDayInterval 5
```
This command modifies the client policy day setting only.


---


### Parameters
#### **ClientPolicyDays**








|Type     |Required|Position|PipelineInput|Aliases                                           |
|---------|--------|--------|-------------|--------------------------------------------------|
|`[Int32]`|false   |named   |False        |PolicyInactiveInterval<br/>ClientPolicyDayInterval|



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



#### **HardwareInventoryDays**








|Type     |Required|Position|PipelineInput|Aliases                                            |
|---------|--------|--------|-------------|---------------------------------------------------|
|`[Int32]`|false   |named   |False        |HWInactiveInterval<br/>HardwareInventoryDayInterval|



#### **HeartbeatDiscoveryDays**








|Type     |Required|Position|PipelineInput|Aliases                                              |
|---------|--------|--------|-------------|-----------------------------------------------------|
|`[Int32]`|false   |named   |False        |DdrInactiveInterval<br/>HeartbeatDiscoveryDayInterval|



#### **HistoryCleanupDays**








|Type     |Required|Position|PipelineInput|Aliases                                      |
|---------|--------|--------|-------------|---------------------------------------------|
|`[Int32]`|false   |named   |False        |CleanUpInterval<br/>HistoryCleanupDayInterval|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SoftwareInventoryDays**








|Type     |Required|Position|PipelineInput|Aliases                                            |
|---------|--------|--------|-------------|---------------------------------------------------|
|`[Int32]`|false   |named   |False        |SWInactiveInterval<br/>SoftwareInventoryDayInterval|



#### **StatusMessageDays**








|Type     |Required|Position|PipelineInput|Aliases                                            |
|---------|--------|--------|-------------|---------------------------------------------------|
|`[Int32]`|false   |named   |False        |StatusInactiveInterval<br/>StatusMessageDayInterval|



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
None





---


### Outputs
* IResultObject[]#SMS_CH_Settings


* IResultObject#SMS_CH_Settings






---


### Notes




---


### Syntax
```PowerShell
Set-CMClientStatusSetting [-ClientPolicyDays <Int32>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-HardwareInventoryDays <Int32>] [-HeartbeatDiscoveryDays <Int32>] [-HistoryCleanupDays <Int32>] [-PassThru] [-SoftwareInventoryDays <Int32>] [-StatusMessageDays <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
