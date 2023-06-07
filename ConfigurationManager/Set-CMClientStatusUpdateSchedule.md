Set-CMClientStatusUpdateSchedule
--------------------------------




### Synopsis
Modifies the schedule interval of the client status update task.



---


### Description

The Set-CMClientStatusUpdateSchedule cmdlet modifies the schedule interval of the client status update task. For more information, see How to Configure Client Status in Configuration Manager (/mem/configmgr/core/clients/deploy/configure-client-status).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [How to Configure Client Status in Configuration Manager](How to Configure Client Status in Configuration Manager)



* [Get-CMClientStatusUpdateSchedule](Get-CMClientStatusUpdateSchedule)



* [Get-CMClientStatusSetting](Get-CMClientStatusSetting)



* [Set-CMClientStatusSetting](Set-CMClientStatusSetting)





---


### Examples
#### Example 1: Modify a client's status update schedule
```PowerShell
PS XYZ:\> Set-CMClientStatusUpdateSchedule -Interval 23 -UnitType Hours
```
This command modifies the client status update schedule.


---


### Parameters
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



#### **Interval**

Specifies the number of hours or days between client status updates.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **UnitType**

Specifies whether the interval between schedule updates is calculated in hours or days. Valid values are: Hours and Days.



Valid Values:

* Days
* Hours






|Type                              |Required|Position|PipelineInput|
|----------------------------------|--------|--------|-------------|
|`[ClientStatusUpdateScheduleUnit]`|true    |named   |False        |



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMClientStatusUpdateSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] -Interval <Int32> -UnitType {Days | Hours} [-Confirm] [-WhatIf] [<CommonParameters>]
```
