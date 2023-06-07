Get-CMClientStatusUpdateSchedule
--------------------------------




### Synopsis
Gets a schedule interval of the client status update task.



---


### Description

The Get-CMClientStatusUpdateSchedule cmdlet gets a schedule interval of the client status update task.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMClientStatusUpdateSchedule](Set-CMClientStatusUpdateSchedule)



* [Get-CMClientStatusSetting](Get-CMClientStatusSetting)



* [Set-CMClientStatusSetting](Set-CMClientStatusSetting)





---


### Examples
#### Example 1: Gets a client status update schedule
```PowerShell
PS XYZ:\> Get-CMClientStatusUpdateSchedule
Interval Unit
-------- ----
       1 Days
```
This command gets a client status update schedule.


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





---


### Inputs
None





---


### Outputs
* ClientStatusUpdateSchedule






---


### Notes




---


### Syntax
```PowerShell
Get-CMClientStatusUpdateSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
