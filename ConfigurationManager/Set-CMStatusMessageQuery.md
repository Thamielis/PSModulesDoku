Set-CMStatusMessageQuery
------------------------




### Synopsis
Changes settings or security scope or deletes messages for a Configuration Manager status message query.



---


### Description

The Set-CMStatusMessageQuery cmdlet changes settings for a Configuration Manager status message query. Status message queries return status messages from a Configuration Manager site database. You can modify a comment, a Windows Management Infrastructure (WMI) expression, or the name of a query.



You can use this cmdlet with the DeleteMessage parameter to delete messages that this query finds.



This cmdlet can also add or remove a security scope for a message query. Every status message query must belong to at least one security scope.



You can specify a name or ID for a query or use the Get-CMStatusMessageQuery (Get-CMStatusMessageQuery.md)cmdlet to obtain a query.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMStatusMessageQuery](Get-CMStatusMessageQuery)



* [New-CMStatusMessageQuery](New-CMStatusMessageQuery)



* [Remove-CMStatusMessageQuery](Remove-CMStatusMessageQuery)





---


### Examples
#### Example 1: Add a security scope
```PowerShell
PS XYZ:\> Set-CMStatusMessageQuery -Name "All Status Messages" -SecurityScopeAction AddMembership -SecurityScopeName "Scope22"
```
This command adds the security scope named Scope22 to the query named All Status Messages.
#### Example 2: Delete messages
```PowerShell
PS XYZ:\> Set-CMStatusMessageQuery -DeleteMessage -Name "All Active Directory Security Groups"
```
This command removes messages found by the query named All Active Directory Security Groups from the Configuration Manager database.
#### Example 3: Rename a query
```PowerShell
PS XYZ:\> Set-CMStatusMessageQuery -Name "All Active Directory Security Groups" -NewName "Western Security Groups"
```
This command renames the query All Active Directory Security Groups. The new name of the query is Western Security Groups.


---


### Parameters
#### **Comment**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |Comments|



#### **DeleteMessage**

Indicates that messages found by this query are deleted from the Configuration Manager database.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Expression**

Specifies an expression in WMI Query Language (WQL).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an ID for a status message query.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |QueryId|



#### **InputObject**

Specifies a status message query object. To obtain a status message query object, use the Get-CMStatusMessageQuery (Get-CMStatusMessageQuery.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name for a status message query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Specifies a new name for a query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMStatusMessageQuery [-Comment <String>] [-DisableWildcardHandling] [-Expression <String>] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStatusMessageQuery [-Comment <String>] [-DisableWildcardHandling] [-Expression <String>] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStatusMessageQuery [-Comment <String>] [-DisableWildcardHandling] [-Expression <String>] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStatusMessageQuery -DeleteMessage [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStatusMessageQuery -DeleteMessage [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStatusMessageQuery -DeleteMessage [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
