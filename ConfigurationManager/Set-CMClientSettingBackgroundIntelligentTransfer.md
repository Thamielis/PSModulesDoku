Set-CMClientSettingBackgroundIntelligentTransfer
------------------------------------------------




### Synopsis
Sets a client setting background intelligent transfer.



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



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableBitsMaxBandwidth**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableDownloadOffSchedule**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **MaxBandwidthBeginHr**








|Type     |Required|Position|PipelineInput|Aliases              |
|---------|--------|--------|-------------|---------------------|
|`[Int32]`|false   |named   |False        |MaxBandwidthValidFrom|



#### **MaxBandwidthEndHr**








|Type     |Required|Position|PipelineInput|Aliases            |
|---------|--------|--------|-------------|-------------------|
|`[Int32]`|false   |named   |False        |MaxBandwidthValidTo|



#### **MaxTransferRateOffSchedule**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MaxTransferRateOnSchedule**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Set-CMClientSettingBackgroundIntelligentTransfer -DefaultSetting [-DisableWildcardHandling] [-EnableBitsMaxBandwidth <Boolean>] [-EnableDownloadOffSchedule <Boolean>] [-ForceWildcardHandling] [-MaxBandwidthBeginHr <Int32>] [-MaxBandwidthEndHr <Int32>] [-MaxTransferRateOffSchedule <Int32>] [-MaxTransferRateOnSchedule <Int32>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingBackgroundIntelligentTransfer [-DisableWildcardHandling] [-EnableBitsMaxBandwidth <Boolean>] [-EnableDownloadOffSchedule <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-MaxBandwidthBeginHr <Int32>] [-MaxBandwidthEndHr <Int32>] [-MaxTransferRateOffSchedule <Int32>] [-MaxTransferRateOnSchedule <Int32>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingBackgroundIntelligentTransfer [-DisableWildcardHandling] [-EnableBitsMaxBandwidth <Boolean>] [-EnableDownloadOffSchedule <Boolean>] [-ForceWildcardHandling] [-MaxBandwidthBeginHr <Int32>] [-MaxBandwidthEndHr <Int32>] [-MaxTransferRateOffSchedule <Int32>] [-MaxTransferRateOnSchedule <Int32>] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
