Get-CMEndpointProtectionSummarizationSchedule
---------------------------------------------




### Synopsis
Gets an Endpoint Protection summarization schedule.



---


### Description

The Get-CMEndpointProtectionSummarizationSchedule cmdlet gets a System Center 2016 Endpoint Protection summarization schedule. For more information about Endpoint Protection summarization schedules, see How to Monitor Endpoint Protection in Configuration Manager (/mem/configmgr/protect/deploy-use/monitor-endpoint-protection).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMEndpointProtectionSummarizationSchedule](Set-CMEndpointProtectionSummarizationSchedule)





---


### Examples
#### Example 1: Get an Endpoint Protection summarization schedule
```PowerShell
PS XYZ:\> Get-CMEndpointProtectionSummarizationSchedule
```
This command gets an Endpoint Protection summarization schedule.


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
* EndpointProtectionSummarizationSchedule






---


### Notes




---


### Syntax
```PowerShell
Get-CMEndpointProtectionSummarizationSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
