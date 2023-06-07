Get-CMConflictingRecord
-----------------------




### Synopsis
Gets conflicting Configuration Manager record objects.



---


### Description

The Get-CMConflictingRecord cmdlet gets one or more conflicting Configuration Manager record objects.



When Configuration Manager recognizes a new client, it uses hardware information to check whether it previously created a record for that computer. For example, you might have reinstalled the operating system. The previous client record still exists with the same hardware information. If you manually resolve conflicts, you have the option to merge the new record with the existing record, create a new record, or create a record as a blocked record. You can also configure Configuration Manager to resolve conflicts automatically.



You can use this cmdlet with the Block-CMConflictingRecord (Block-CMConflictingRecord.md) cmdlet or the [Merge-CMConflictingRecord](Merge-CMConflictingRecord.md)cmdlet. You can get all the outstanding conflicts for Configuration Manager or specify a conflict by name or by ID.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Block-CMConflictingRecord](Block-CMConflictingRecord)



* [Merge-CMConflictingRecord](Merge-CMConflictingRecord)





---


### Examples
#### Example 1: Get all conflicting records
```PowerShell
PS XYZ:\> Get-CMConflictingRecord
```
This command gets all the unresolved conflicts for Configuration Manager.
#### Example 2: Get a named conflicting record
```PowerShell
PS XYZ:\> Get-CMConflictingRecord -Name "CR07"
```
This command gets a conflict named CR07.


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



#### **Name**

Specifies a name for the conflicting records.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|false   |named   |False        |AgentName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_PendingRegistrationRecord


* IResultObject#SMS_PendingRegistrationRecord






---


### Notes




---


### Syntax
```PowerShell
Get-CMConflictingRecord [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMConflictingRecord [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
