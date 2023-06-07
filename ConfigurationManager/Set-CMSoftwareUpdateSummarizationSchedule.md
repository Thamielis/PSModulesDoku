Set-CMSoftwareUpdateSummarizationSchedule
-----------------------------------------




### Synopsis
Sets how often Configuration Manager summarizes the status of updates.



---


### Description

The Set-CMSoftwareUpdateSummarizationSchedule cmdlet sets how often Configuration Manager summarizes the status of software updates for all the Configuration Manager sites. You can set the summary to run on an interval defined in days, hours, or minutes. You can use the Invoke-CMSoftwareUpdateSummarization (Invoke-CMSoftwareUpdateSummarization.md)cmdlet to run the summarization immediately.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateSummarizationSchedule](Get-CMSoftwareUpdateSummarizationSchedule)



* [Invoke-CMSoftwareUpdateSummarization](Invoke-CMSoftwareUpdateSummarization)





---


### Examples
#### Example 1: Schedule summarization interval and unit
```PowerShell
PS XYZ:\> Set-CMSoftwareUpdateSummarizationSchedule -Interval 5 -Unit Days
```
This command sets the update summarization schedule to run every five days.
#### Example 2: Change schedule interval
```PowerShell
PS XYZ:\> Set-CMSoftwareUpdateSummarizationSchedule -Interval 7
```
This command changes the interval for the update summarization schedule to seven. The command does not change the unit.


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



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
|`[SummarizationScheduleUnit]`|true    |named   |False        |



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
Set-CMSoftwareUpdateSummarizationSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] -Interval <Int32> [-PassThru] -Unit {Days | Hours | Minutes} [-Confirm] [-WhatIf] [<CommonParameters>]
```
