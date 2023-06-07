Get-CMStatusSummarizer
----------------------




### Synopsis
Gets a status summarizer object for Configuration Manager.



---


### Description

The Get-CMStatusSummarizer cmdlet gets a status summarizer object. The Configuration Manager status summarizers apply to the areas of application deployment, application statistics, component status, and site system status.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMStatusSummarizer](Set-CMStatusSummarizer)





---


### Examples
#### Example 1: Get a status summarizer
```PowerShell
PS XYZ:\> Get-CMStatusSummarizer -SiteCode "CM1" -StatusSummarizerType ComponentStatusSummarizer
```
This command gets the status summarizer for the component status.


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



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |SiteName|



#### **SiteCode**

Specifies a site code for the Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StatusSummarizerType**

Specifies a status summarization type.



Valid Values:

* ApplicationDeploymentSummarizer
* ApplicationStatisticsSummarizer
* ComponentStatusSummarizer
* SiteSystemStatusSummarizer






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[StatusSummarizerType]`|true    |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject#SMS_SummarizationSettings


* IResultObject[]#SMS_SummarizationSettings


* IResultObject#SMS_SCI_Component


* IResultObject[]#SMS_SCI_Component






---


### Notes




---


### Syntax
```PowerShell
Get-CMStatusSummarizer [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-SiteCode <String>] [<CommonParameters>]
```
```PowerShell
Get-CMStatusSummarizer [-DisableWildcardHandling] [-ForceWildcardHandling] -StatusSummarizerType {ApplicationDeploymentSummarizer | ApplicationStatisticsSummarizer | ComponentStatusSummarizer | SiteSystemStatusSummarizer} [<CommonParameters>]
```
