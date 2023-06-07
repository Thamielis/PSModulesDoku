Invoke-CMSoftwareUpdateSummarization
------------------------------------




### Synopsis
Runs the Configuration Manager software update summarization.



---


### Description

The Invoke-CMSoftwareUpdateSummarization cmdlet runs the software update summarization in Configuration Manager immediately. Configuration Manager summarizes software update status on a regular schedule. This cmdlet does not reset the time for the next automatic summarization.



You can use the Get-CMSoftwareUpdateSummarizationSchedule cmdlet to view the current schedule and the Set-CMSoftwareUpdateSummarizationSchedule (Set-CMSoftwareUpdateSummarizationSchedule.md)cmdlet to change the schedule.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateSummarizationSchedule](Get-CMSoftwareUpdateSummarizationSchedule)



* [Set-CMSoftwareUpdateSummarizationSchedule](Set-CMSoftwareUpdateSummarizationSchedule)





---


### Examples
#### Example 1: Run software update summarization
```PowerShell
PS XYZ:\>Invoke-CMSoftwareUpdateSummarization
```
This command runs the software update summarization immediately, instead of waiting for the next scheduled time.


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
Invoke-CMSoftwareUpdateSummarization [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
