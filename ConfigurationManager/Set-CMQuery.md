Set-CMQuery
-----------




### Synopsis
Configure a Configuration Manager query.



---


### Description

Use this cmdlet to configure a query in Configuration Manager. Configuration Manager queries define a WMI Query Language (WQL) expression to get information from the site database based on the criteria you provide. WQL is similar to SQL, but still goes through the SMS Provider instead of directly to the database. So WQL still abides by your role-based access configuration.



Queries can return most types of Configuration Manager objects, which include computers, sites, collections, applications, and inventory data. For more information, see Introduction to queries in Configuration Manager (/mem/configmgr/core/servers/manage/introduction-to-queries).



By default, Configuration Manager includes several queries. You can use the Get-CMQuery (Get-CMQuery.md) cmdlet to review the default queries. For more examples of WQL expressions, see [Example WQL queries](/mem/configmgr/core/servers/manage/create-queries#BKMK_Example).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMQuery](Export-CMQuery)



* [Get-CMQuery](Get-CMQuery)



* [Import-CMQuery](Import-CMQuery)



* [Invoke-CMQuery](Invoke-CMQuery)



* [New-CMQuery](New-CMQuery)



* [Remove-CMQuery](Remove-CMQuery)



* [Introduction to queries in Configuration Manager](Introduction to queries in Configuration Manager)





---


### Examples
#### Example 1: Rename a query
```PowerShell
Get-CMQuery -Name "My systems" | Set-CMQuery -NewName "My systems v2"
```

#### Example 2: Change the query to prompt for a limiting collection
```PowerShell
Set-CMQuery -Name "Windows 10" -LimitToCollectionId "<Prompt>"
```



---


### Parameters
#### **Comment**

Specify an optional comment to further identify the query in the site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Expression**

Specify the WQL statement that defines the attributes to display in the results and the criteria to limit the results.


WQL statements often include double quotation marks (`"`), so set this parameter's value as a string enclosed in single quotation marks (`'`).


For more examples, see Example WQL queries (/mem/configmgr/core/servers/manage/create-queries#BKMK_Example).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the query to configure. For example, `"XYZ00006"`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |QueryId|



#### **InputObject**

Specify a query object to configure. To get this object, use the Get-CMQuery (Get-CMQuery.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **LimitToCollectionId**

Specify how to configure collection limiting for this query:


* Not collection limited : Set this parameter's value to a blank string (`""`). Don't use the `$null` built-in variable. - Limit to collection : Specify the ID of a collection. For example, `"SMSDM003"` for the All Desktop and Server Clients collection. - Prompt for collection : Set this parameter's value to `"<Prompt>"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specify the name of the query to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Specify a new name to rename the query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **TargetClassName**

Specify the name of the object class that you want the query to return. There are many object types available. The following table lists several common class names with the description from the Configuration Manager console:


|Class name  |Description  | |---------|---------| |`SMS_R_System`|System resource| |`SMS_Program`|Program| |`SMS_R_UserGroup`|User group resource| |`SMS_R_User`|User resource| |`SMS_SiteAndSubsites`|Site and subsites| |`SMS_R_UnknownSystem`|Unknown computer|






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Set-CMQuery [-Comment <String>] [-DisableWildcardHandling] [-Expression <String>] [-ForceWildcardHandling] -Id <String> [-LimitToCollectionId <String>] [-NewName <String>] [-PassThru] [-TargetClassName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMQuery [-Comment <String>] [-DisableWildcardHandling] [-Expression <String>] [-ForceWildcardHandling] -InputObject <IResultObject> [-LimitToCollectionId <String>] [-NewName <String>] [-PassThru] [-TargetClassName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMQuery [-Comment <String>] [-DisableWildcardHandling] [-Expression <String>] [-ForceWildcardHandling] [-LimitToCollectionId <String>] -Name <String> [-NewName <String>] [-PassThru] [-TargetClassName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
