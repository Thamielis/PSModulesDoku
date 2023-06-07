Import-CMQuery
--------------




### Synopsis
Import a query to Configuration Manager.



---


### Description

Use this cmdlet to import one or more queries to the Configuration Manager site. Configuration Manager queries define a WMI Query Language (WQL) expression to get information from the site database based on the criteria you provide.



You import a query that you exported from another site. For example, export a query from a test lab, and then import it to a production environment.



Use the Export-CMQuery (Export-CMQuery.md) cmdlet to export the query from another site. Configuration Manager exports the query to a managed object format (MOF)file.



For more information, see Introduction to queries in Configuration Manager (/mem/configmgr/core/servers/manage/introduction-to-queries).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMQuery](Get-CMQuery)



* [Export-CMQuery](Export-CMQuery)



* [Invoke-CMQuery](Invoke-CMQuery)



* [New-CMQuery](New-CMQuery)



* [Remove-CMQuery](Remove-CMQuery)



* [Set-CMQuery](Set-CMQuery)



* [Introduction to queries in Configuration Manager](Introduction to queries in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Import-CMQuery -ImportFilePath "C:\Export\Query.nof"
```



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



#### **ImportFilePath**

Specify the path to the file to import. The file extension is .mof .






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|true    |0       |False        |FileName<br/>FilePath<br/>Path|



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
Import-CMQuery [-ImportFilePath] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
