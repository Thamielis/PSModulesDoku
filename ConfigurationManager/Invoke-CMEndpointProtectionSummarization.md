Invoke-CMEndpointProtectionSummarization
----------------------------------------




### Synopsis
Retrieves summary status data about Endpoint Protection.



---


### Description

The Invoke-CMEndpointProtectionSummarization cmdlet retrieves summary status data about System Center 2016 Endpoint Protection in Configuration Manager. This data helps you monitor Endpoint Protection in your Configuration Manager hierarchy.



For more information about configuring and monitoring Endpoint Protection, see How To Monitor Endpoint Configuration In Configuration Manager (/mem/configmgr/protect/deploy-use/monitor-endpoint-protection).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [How To Monitor Endpoint Configuration In Configuration Manager](How To Monitor Endpoint Configuration In Configuration Manager)



* [Get-CMEndpointProtectionSummarizationSchedule](Get-CMEndpointProtectionSummarizationSchedule)



* [Set-CMEndpointProtectionSummarizationSchedule](Set-CMEndpointProtectionSummarizationSchedule)





---


### Examples
#### Example 1: Invoke summarization for Endpoint Protection
```PowerShell
PS XYZ:\>Invoke-CMEndpointProtectionSummarization -Confirm
```
This command gets summary data about Endpoint Protection status after you confirm that you want to run the command.


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
Invoke-CMEndpointProtectionSummarization [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
