New-CMEmbeddedPropertyList
--------------------------




### Synopsis
Creates an embedded property list.



---


### Description

The New-CMEmbeddedPropertyList cmdlet creates an embedded property list.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMEmbeddedObjectInstance](New-CMEmbeddedObjectInstance)



* [New-CMEmbeddedProperty](New-CMEmbeddedProperty)





---


### Examples
#### Example 1: Create an embedded property list
```PowerShell
PS ABC:\> New-CMEmbeddedPropertyList -PropertyListName "AD Containers" -Value "LDAP://CN=Computers,DC=Contoso,DC=com","LDAP://OU=testUnit,DC=Contoso,DC=com"
```
This command creates an embedded property list with the name AD Containers, and adds the specified LDAP values.


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



#### **PropertyListName**

Specifies a name for the property list.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **Value**

Specifies an array of values for the property list.






|Type        |Required|Position|PipelineInput|Aliases|
|------------|--------|--------|-------------|-------|
|`[Object[]]`|false   |named   |False        |Values |



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
New-CMEmbeddedPropertyList [-DisableWildcardHandling] [-ForceWildcardHandling] -PropertyListName <String> [-Value <Object[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
