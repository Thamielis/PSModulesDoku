Block-CMConflictingRecord
-------------------------




### Synopsis
Creates a blocked Configuration Manager record for client that has a conflicting record.



---


### Description

The Block-CMConflictingRecord cmdlet blocks a record for a client that has a conflicting record in Configuration Manager.



When Configuration Manager recognizes a new client, it uses hardware information to check whether it previously created a record for that computer. For example, you might have reinstalled the operating system. The previous client record still exists with the same hardware information. If you manually resolve conflicts, you have the option to merge the new record with the existing record, create a new record, or create a record as a blocked record. You can also configure Configuration Manager to resolve conflicts automatically.



You can specify a conflict by using a name or ID or you can use the Get-CMConflictingRecord (Get-CMConflictingRecord.md)cmdlet to obtain one.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMConflictingRecord](Get-CMConflictingRecord)



* [Merge-CMConflictingRecord](Merge-CMConflictingRecord)





---


### Examples
#### Example 1: Create a blocked record for a named conflict
```PowerShell
PS XYZ:\>Block-CMConflictingRecord -Name "CR07"
```
This command creates a blocked record for the conflict named CR07.
#### Example 2: Create a blocked record by using a variable
```PowerShell
PS XYZ:\> $CMCR = Get-CMConflictingRecord -Name "CR07"
PS XYZ:\> Block-CMConflictingRecord -ConflictingRecord $CMCR
```
The first command gets a conflicting record named CR07 and saves it in the $CMCR variable.


The second command creates a blocked record for the conflict in $CMCR.


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
|`[String]`|true    |named   |False        |SmsId  |



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases          |
|-----------------|--------|--------|--------------|-----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ConflictingRecord|



#### **Name**

Specifies a name for the conflicting records.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |AgentName|



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
Block-CMConflictingRecord [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Block-CMConflictingRecord [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Block-CMConflictingRecord [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
