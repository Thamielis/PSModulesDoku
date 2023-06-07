Get-CMQuery
-----------




### Synopsis
Get a Configuration Manager query.



---


### Description

Use this cmdlet to get a query from the Configuration Manager site. Configuration Manager queries define a WMI Query Language (WQL) expression to get information from the site database based on the criteria you provide. WQL is similar to SQL, but still goes through the SMS Provider instead of directly to the database. So WQL still abides by your role-based access configuration.



Queries can return most types of Configuration Manager objects, which include computers, sites, collections, applications, and inventory data. For more information, see Introduction to queries in Configuration Manager (/mem/configmgr/core/servers/manage/introduction-to-queries).



By default, Configuration Manager includes several queries. You can use this cmdlet to review the default queries.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMQuery](Export-CMQuery)



* [Import-CMQuery](Import-CMQuery)



* [Invoke-CMQuery](Invoke-CMQuery)



* [New-CMQuery](New-CMQuery)



* [Remove-CMQuery](Remove-CMQuery)



* [Set-CMQuery](Set-CMQuery)



* [Introduction to queries in Configuration Manager](Introduction to queries in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Get-CMQuery -Name "*ConfigMgr clients *"
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



#### **Id**

Specify the ID of the query to get. For example, `"XYZ00006"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specify the name of the query to get.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_Query


* IResultObject#SMS_Query






---


### Notes




---


### Syntax
```PowerShell
Get-CMQuery [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [<CommonParameters>]
```
```PowerShell
Get-CMQuery [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
