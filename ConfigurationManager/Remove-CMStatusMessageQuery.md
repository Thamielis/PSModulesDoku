Remove-CMStatusMessageQuery
---------------------------




### Synopsis
Removes a Configuration Manager status message query.



---


### Description

The Remove-CMStatusMessageQuery cmdlet removes  a status message query from Configuration Manager. Status message queries return status messages from the Configuration Manager site database.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMStatusMessageQuery](Get-CMStatusMessageQuery)



* [New-CMStatusMessageQuery](New-CMStatusMessageQuery)



* [Set-CMStatusMessageQuery](Set-CMStatusMessageQuery)





---


### Examples
#### Example 1: Remove a named query
```PowerShell
PS XYZ:\> Remove-CMStatusMessageQuery -Name "All Audit Status Messages from a Specific Site"
Remove
Are you sure you wish to remove StatusMessageQuery: Name="All Audit Status Messages from a Specific Site"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```
This command removes a query named All Audit Status Messages from a Specific Site. The command does not include the Force parameter, so the cmdlet prompts you before it removes the query.
#### Example 2: Remove a query that has a specified ID
```PowerShell
PS XYZ:\> Remove-CMStatusMessageQuery -Id "CM100008" -Force
```
This command removes the query that has an ID of CM100008. The command includes the Force parameter, so the cmdlet does not prompt you for confirmation.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an ID of a status message query.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |QueryId|



#### **InputObject**

Specifies a status message query object. To obtain a status message query object, use the Get-CMStatusMessageQuery cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name of a status message query.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMStatusMessageQuery [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMStatusMessageQuery [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMStatusMessageQuery [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
