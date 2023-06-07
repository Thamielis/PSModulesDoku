Set-CMEndpointProtectionSummarizationSchedule
---------------------------------------------




### Synopsis
Modifies an Endpoint Protection summarization schedule.



---


### Description

The Set-CMEndpointProtectionSummarizationSchedule cmdlet modifies the settings of an System Center 2016 Endpoint Protection summarization schedule. For more information about Endpoint Protection summarization schedules, see How to Monitor Endpoint Protection in Configuration Manager (/mem/configmgr/protect/deploy-use/monitor-endpoint-protection).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMEndpointProtectionSummarizationSchedule](Get-CMEndpointProtectionSummarizationSchedule)





---


### Examples
#### Example 1: Modify an Endpoint Protection summarization schedules
```PowerShell
PS XYZ:\> Set-CMEndpointProtectionSummarizationSchedule -Interval 10 -UnitType "Days"
```
This command modifies the interval and unit values to specify that 10 days pass before the Endpoint Protection Summarization Schedule runs again.


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

Specifies an amount of time, as an integer. This value works with the unit type you specify in the Unit parameter. Valid values for this parameter depend on the unit that you select:


* Minutes: 10 through 59.


* Hours: 1 through 23.


* Days: 1 through 31.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **Unit**

Specifies a unit to use to define an interval for the summarization schedule. The acceptable values for this parameter are:


* Days


* Hours


* Minutes



Valid Values:

* Minutes
* Hours
* Days






|Type                         |Required|Position|PipelineInput|
|-----------------------------|--------|--------|-------------|
|`[SummarizationScheduleUnit]`|false   |named   |False        |



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
Set-CMEndpointProtectionSummarizationSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] -Interval <Int32> [-Unit {Minutes | Hours | Days}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
