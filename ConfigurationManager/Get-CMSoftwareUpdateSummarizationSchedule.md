Get-CMSoftwareUpdateSummarizationSchedule
-----------------------------------------




### Synopsis
Displays the Configuration Manager schedule for software update summarization.



---


### Description

The Get-CMSoftwareUpdateSummarizationSchedule cmdlet displays the current schedule for software update summarization for Configuration Manager. You can use the Set-CMSoftwareUpdateSummarizationSchedule (Set-CMSoftwareUpdateSummarizationSchedule.md)cmdlet to change the schedule. You can use the Invoke-CMSoftwareUpdateSummarization (Invoke-CMSoftwareUpdateSummarization.md)cmdlet to run the summarization immediately.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMSoftwareUpdateSummarizationSchedule](Set-CMSoftwareUpdateSummarizationSchedule)



* [Invoke-CMSoftwareUpdateSummarization](Invoke-CMSoftwareUpdateSummarization)





---


### Examples
#### Example 1: Display the summarization schedule
```PowerShell
PS XYZ:\> Get-CMSoftwareUpdateSummarizationSchedule
                               Interval                                    Unit
                               --------                                    ----
                                     12                                   Hours
```
This command displays the summarization schedule for software updates. In this case, the schedule is every 12 hours.


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



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* SoftwareUpdateSummarizationSchedule






---


### Notes




---


### Syntax
```PowerShell
Get-CMSoftwareUpdateSummarizationSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [<CommonParameters>]
```
