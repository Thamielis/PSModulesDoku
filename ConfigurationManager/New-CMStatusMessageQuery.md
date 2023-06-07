New-CMStatusMessageQuery
------------------------




### Synopsis
Creates a status message query.



---


### Description

The New-CMStatusMessageQuery cmdlet creates a status message query in Configuration Manager. Status message queries in Configuration Manager return status messages from the site database. All major Configuration Manager components generate status messages.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMStatusMessageQuery](Get-CMStatusMessageQuery)



* [Set-CMStatusMessageQuery](Set-CMStatusMessageQuery)



* [Remove-CMStatusMessageQuery](Remove-CMStatusMessageQuery)





---


### Examples
#### Example 1: Create a status message query
```PowerShell
PS XYZ:\> New-CMStatusMessageQuery -Name "Client Component Configuration Changes and Fatal Errors" -Expression "select stat.*, ins.*, att1.*, stat.Time from SMS_StatusMessage as stat left join SMS_StatMsgInsStrings as ins on stat.RecordID = ins.RecordID left join SMS_StatMsgAttributes as att1 on stat.RecordID = att1.RecordID where stat.ModuleName = 'SMS Client' and stat.MessageID = 669 and stat.SiteCode = ##PRM:SMS_StatusMessage.SiteCode## and stat.Time >= ##PRM:SMS_StatusMessage.Time## order by stat.Time desc"
```
This command creates a status message query named Client Component Configuration Changes and Fatal Errors. The Expression parameter specifies the WMI Query Language (WQL) text for the query.


---


### Parameters
#### **Comment**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |Comments|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Expression**

Specifies WMI Query Language (WQL) text for the query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specifies a name for the status message query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
* IResultObject#SMS_Query






---


### Notes




---


### Syntax
```PowerShell
New-CMStatusMessageQuery [-Comment <String>] [-DisableWildcardHandling] [-Expression <String>] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
