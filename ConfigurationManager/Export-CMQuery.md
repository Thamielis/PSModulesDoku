Export-CMQuery
--------------




### Synopsis
Export a query from Configuration Manager.



---


### Description

Use this cmdlet to export a query from Configuration Manager. Configuration Manager queries define a WMI Query Language (WQL) expression to get information from the site database based on the criteria you provide.



You can export a query to copy it from one site to another. For example, to copy a query from a test lab to a production environment.



Configuration Manager exports the query to a managed object format (MOF) file. You can then use the Import-CMQuery (Import-CMQuery.md)cmdlet to import the query to another site.



For more information, see Introduction to queries in Configuration Manager (/mem/configmgr/core/servers/manage/introduction-to-queries).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMQuery](Get-CMQuery)



* [Import-CMQuery](Import-CMQuery)



* [Invoke-CMQuery](Invoke-CMQuery)



* [New-CMQuery](New-CMQuery)



* [Remove-CMQuery](Remove-CMQuery)



* [Set-CMQuery](Set-CMQuery)



* [Introduction to queries in Configuration Manager](Introduction to queries in Configuration Manager)





---


### Examples
#### Example 1: Export a query
```PowerShell
Export-CMQuery -Name "My systems" -ExportFilePath "C:\export\query.mof"
```

#### Example 2: Export a query with a comment
```PowerShell
Export-CMQuery -Name "My Systems" -ExportFilePath "C:\Export\Query.mof" -Comment "This is a comment"

// Comments :
//
// This is a comment
```



---


### Parameters
#### **Comment**

Specify an optional comment. Configuration Manager includes the comment in the MOF file. If you use the Configuration Manager console to import the query, the comment displays in the Import Objects Wizard.


This comment has a limit of 1024 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExportFilePath**

Specify the path to the exported file. The file extension is .mof . It can be a local or network path. Create the target folder first.






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>Path|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the query to export. For example, `XYZ00006`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |QueryId|



#### **InputObject**

Specify a query object to export. To get this object, use the Get-CMQuery (Get-CMQuery.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |0       |True (ByValue)|Query  |



#### **Name**

Specify the name of the query to export.






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
Export-CMQuery [-Comment <String>] [-DisableWildcardHandling] -ExportFilePath <String> [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMQuery [-InputObject] <IResultObject> [-Comment <String>] [-DisableWildcardHandling] -ExportFilePath <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMQuery [-Comment <String>] [-DisableWildcardHandling] -ExportFilePath <String> [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
