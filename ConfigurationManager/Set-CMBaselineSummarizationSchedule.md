Set-CMBaselineSummarizationSchedule
-----------------------------------




### Synopsis
Configures the summarization schedule for configuration baseline data.



---


### Description

The Set-CMBaselineSummarizationSchedule cmdlet configures the schedule by which the configuration baseline data in the Configuration Manager is updated with the latest information from the site database.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBaselineSummarizationSchedule](Get-CMBaselineSummarizationSchedule)



* [Invoke-CMBaselineSummarization](Invoke-CMBaselineSummarization)





---


### Examples
#### Example 1: Set the configuration baseline update schedule
```PowerShell
PS XYZ:\> Set-CMBaselineSummarizationSchedule -Interval 6 -Unit "Hours"
```
This command schedules Configuration Manager to automatically update the configuration baseline data every six hours.


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

Specifies a unit to use to define an interval for the summarization schedule. Valid values are:


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
Set-CMBaselineSummarizationSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] -Interval <Int32> [-Unit {Minutes | Hours | Days}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
