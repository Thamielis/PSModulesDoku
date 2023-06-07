Invoke-CMBaselineSummarization
------------------------------




### Synopsis
Updates configuration baseline data.



---


### Description

The Invoke-CMBaselineSummarization cmdlet updates data in configuration baselines in Configuration Manager with the latest data from the site database. This action might take several minutes to complete.



You can use the Set-CMBaselineSummarizationSchedule (Set-CMBaselineSummarizationSchedule.md)cmdlet to configure a schedule by which the data is updated with the latest information from the site database.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMBaselineSummarizationSchedule](Set-CMBaselineSummarizationSchedule)



* [Get-CMBaselineSummarizationSchedule](Get-CMBaselineSummarizationSchedule)





---


### Examples
#### Example 1: Update configuration baseline data
```PowerShell
PS XYZ:\>Invoke-CMBaselineSummarization
```
This command updates data in configuration baselines with the latest data from the site database.


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
Invoke-CMBaselineSummarization [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
