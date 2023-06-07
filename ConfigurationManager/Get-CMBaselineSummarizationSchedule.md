Get-CMBaselineSummarizationSchedule
-----------------------------------




### Synopsis
Gets the summarization schedule for configuration baseline data.



---


### Description

The Get-CMBaselineSummarizationSchedule cmdlet gets the schedule by which the configuration baseline data in the Configuration Manager is updated with the latest information from the site database.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMBaselineSummarizationSchedule](Set-CMBaselineSummarizationSchedule)



* [Invoke-CMBaselineSummarization](Invoke-CMBaselineSummarization)





---


### Examples
#### Example 1: Get the update schedule for configuration baseline data
```PowerShell
PS XYZ:\> Get-CMBaselineSummarizationSchedule
```
This command gets the update schedule for configuration baseline data.


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
* BaselineSummarizationSchedule






---


### Notes




---


### Syntax
```PowerShell
Get-CMBaselineSummarizationSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
