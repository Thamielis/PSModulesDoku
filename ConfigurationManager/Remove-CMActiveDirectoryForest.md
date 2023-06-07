Remove-CMActiveDirectoryForest
------------------------------




### Synopsis
Removes an Active Directory forest object from Configuration Manager.



---


### Description

The Remove-CMActiveDirectoryForest cmdlet removes an Active Directory forest object from Configuration Manager. You can specify an Active Directory forest by using the ID property or the fully qualified domain name (FQDN), or you can supply the Active Directory forest itself.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMActiveDirectoryForest](New-CMActiveDirectoryForest)



* [Get-CMActiveDirectoryForest](Get-CMActiveDirectoryForest)



* [Set-CMActiveDirectoryForest](Set-CMActiveDirectoryForest)





---


### Examples
#### Example 1: Remove an Active Directory forest object by ID
```PowerShell
PS XYZ:\> Remove-CMActiveDirectoryForest -Id "16777217"
```
This command removes an Active Directory forest object that has the ID 16777217.


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



#### **InputObject**

Specifies an Active Directory forest object in Configuration Manager.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |0       |False        |ForestFqdn|



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
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMActiveDirectoryForest [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMActiveDirectoryForest [-Name] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
