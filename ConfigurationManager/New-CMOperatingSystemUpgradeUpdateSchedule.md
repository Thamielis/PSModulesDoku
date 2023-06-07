New-CMOperatingSystemUpgradeUpdateSchedule
------------------------------------------




### Synopsis
Creates an operating system upgrade update schedule.



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
#### **ContinueOnError**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CustomSchedule**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



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



#### **Id**








|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RemoveSupersededUpdates**

{{ Fill RemoveSupersededUpdates Description }}






|Type       |Required|Position|PipelineInput|Aliases|
|-----------|--------|--------|-------------|-------|
|`[Boolean]`|false   |named   |False        |CleanUp|



#### **RunNow**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SoftwareUpdate**








|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|true    |named   |False        |



#### **UpdateDistributionPoint**








|Type       |Required|Position|PipelineInput|Aliases                                                       |
|-----------|--------|--------|-------------|--------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |UpdateDistributionPointsWithImage<br/>UpdateDistributionPoints|



#### **Utc**








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
* IResultObject#SMS_ImageServicingSchedule






---


### Notes




---


### Syntax
```PowerShell
New-CMOperatingSystemUpgradeUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Utc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemUpgradeUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Utc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemUpgradeUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Utc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemUpgradeUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Utc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemUpgradeUpdateSchedule [-ContinueOnError <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemUpgradeUpdateSchedule [-ContinueOnError <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemUpgradeUpdateSchedule [-ContinueOnError <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemUpgradeUpdateSchedule [-ContinueOnError <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
