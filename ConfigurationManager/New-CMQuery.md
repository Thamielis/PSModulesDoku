New-CMQuery
-----------




### Synopsis
Create a Configuration Manager query.



---


### Description

Use this cmdlet to create a query in Configuration Manager.



Configuration Manager queries define a WMI Query Language (WQL) expression to get information from the site database based on the criteria you provide. WQL is similar to SQL, but still goes through the SMS Provider instead of directly to the database. So WQL still abides by your role-based access configuration.



Queries can return most types of Configuration Manager objects, which include computers, sites, collections, applications, and inventory data. For more information, see Introduction to queries in Configuration Manager (/mem/configmgr/core/servers/manage/introduction-to-queries).



By default, Configuration Manager includes several queries. You can use the Get-CMQuery (Get-CMQuery.md) cmdlet to review the default queries. For more examples of WQL expressions, see [Example WQL queries](/mem/configmgr/core/servers/manage/create-queries#BKMK_Example).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMQuery](Export-CMQuery)



* [Get-CMQuery](Get-CMQuery)



* [Import-CMQuery](Import-CMQuery)



* [Invoke-CMQuery](Invoke-CMQuery)



* [Remove-CMQuery](Remove-CMQuery)



* [Set-CMQuery](Set-CMQuery)



* [Introduction to queries in Configuration Manager](Introduction to queries in Configuration Manager)





---


### Examples
#### Example 1: Create a new query for servers of a specific version
```PowerShell
New-CMQuery -Name "Server 2016" -Expression 'select SMS_R_System.Name, SMS_R_System.LastLogonUserName, SMS_G_System_OPERATING_SYSTEM.Caption from SMS_R_System inner join SMS_G_System_OPERATING_SYSTEM on SMS_G_System_OPERATING_SYSTEM.ResourceID = SMS_R_System.ResourceId where SMS_G_System_OPERATING_SYSTEM.Caption like "Microsoft Windows Server 2012%"' -TargetClassName "SMS_R_System" -LimitToCollectionId "SMS00001"
```

#### Example 2: Create a query for desktop devices
```PowerShell
New-CMQuery -Name "Desktop devices" -Expression 'select SMS_R_SYSTEM.ResourceID,SMS_R_SYSTEM.ResourceType,SMS_R_SYSTEM.Name,SMS_R_SYSTEM.SMSUniqueIdentifier,SMS_R_SYSTEM.ResourceDomainORWorkgroup,SMS_R_SYSTEM.Client from SMS_R_System inner join SMS_G_System_SYSTEM_ENCLOSURE on SMS_G_System_SYSTEM_ENCLOSURE.ResourceID = SMS_R_System.ResourceId where SMS_G_System_SYSTEM_ENCLOSURE.ChassisTypes in ( "3", "4", "5","6", "7", "15","16")' -TargetClassName "SMS_R_System" -LimitToCollectionId "XYZ000049"
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
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **LimitToCollectionId**

Specify how to configure collection limiting for this query:


* Not collection limited : Set this parameter's value to a blank string (`""`). Don't use the `$null` built-in variable. - Limit to collection : Specify the ID of a collection. For example, `"SMSDM003"` for the All Desktop and Server Clients collection. - Prompt for collection : Set this parameter's value to `"<Prompt>"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specify the name of the query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
None





---


### Outputs
* IResultObject#SMS_Query






---


### Notes




---


### Syntax
```PowerShell
New-CMQuery [-Comment <String>] [-DisableWildcardHandling] -Expression <String> [-ForceWildcardHandling] [-LimitToCollectionId <String>] -Name <String> [-TargetClassName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
