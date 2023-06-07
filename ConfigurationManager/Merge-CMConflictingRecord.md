Merge-CMConflictingRecord
-------------------------




### Synopsis
Merges a new Configuration Manager client record with a conflicting client record.



---


### Description

The Merge-CMConflictingRecord cmdlet merges a new Configuration Manager client record with a conflicting client record that has the same hardware information.



When Configuration Manager recognizes a new client, it uses hardware information to check whether it previously created a record for that computer. For example, you might have reinstalled the operating system. The previous client record still exists with the same hardware information. If you manually resolve conflicts, you have the option to merge the new record with the existing record, create a new record, or create a record as a blocked record. You can also configure Configuration Manager to resolve conflicts automatically.



You can specify conflicting records by using a name or ID or you can specify a site code to merge each of the unresolved conflicting records for that site.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Block-CMConflictingRecord](Block-CMConflictingRecord)



* [Get-CMConflictingRecord](Get-CMConflictingRecord)





---


### Examples
#### Example 1: Merge conflicting records for a site
```PowerShell
PS XYZ:\>Merge-CMConflictingRecords -SiteCode "CM2"
```
This command merges each of the conflicting records for the specified Configuration Manager site.
#### Example 2: Merge records for a named conflict
```PowerShell
PS XYZ:\>Merge-CMConflictingRecords -Name "CR07"
```
This command merges the conflicting records named CR07.


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



#### **Id**

Specifies an ID for the conflicting records.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Smsid  |



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name for the conflicting records.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |AgentName|



#### **SiteCode**

Specifies a site code for a Configuration Manager site. This cmdlet merges the conflicting records for this site.






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
Merge-CMConflictingRecord [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Merge-CMConflictingRecord [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Merge-CMConflictingRecord [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Merge-CMConflictingRecord [-DisableWildcardHandling] [-ForceWildcardHandling] -SiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
