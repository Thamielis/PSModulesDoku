Add-CMUserCollectionQueryMembershipRule
---------------------------------------




### Synopsis
Add a query membership rule to a user collection.



---


### Description

Use this cmdlet to add a query membership rule to a user collection. A query rule lets you dynamically update the membership of a collection based on a query that is run on a schedule. You can't add membership rules to default collections. Any collection that you target should have an ID that starts with the site code, not `SMS`. For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMUserCollectionQueryMembershipRule](Get-CMUserCollectionQueryMembershipRule)



* [Remove-CMUserCollectionQueryMembershipRule](Remove-CMUserCollectionQueryMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Add-CMDeviceCollectionQueryMembershipRule](Add-CMDeviceCollectionQueryMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Add a query membership rule
```PowerShell
$wql = "select SMS_R_USER.ResourceID,SMS_R_USER.ResourceType,SMS_R_USER.Name,SMS_R_USER.UniqueUserName,SMS_R_USER.WindowsNTDomain from SMS_R_User"

Add-CMUserCollectionQueryMembershipRule -CollectionName "Remote Users" -QueryExpression $wql -RuleName "Remote users by domain"
```



---


### Parameters
#### **CollectionId**

Specify the ID of the user collection to add the rule. This value is the CollectionID property, for example, `XYZ00012`. Since you can't add membership rules to default collections, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specify the name of the user collection to add the rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **InputObject**

Specify an object for the user collection to add the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **QueryExpression**

Specify the WMI Query Language (WQL) expression that the site uses to update the user collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RuleName**

Specify the name of the query rule to add to the collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ValidateQueryHasResult**

Add this parameter to test the query expression before adding the rule. When the cmdlet runs with this parameter, if the query expression has no results, the cmdlet returns the following error message: `No object corresponds to the specified parameters.` In this case, the query isn't added to the collection.


If you know the query currently returns zero results, but still want to add the rule, don't use this parameter.






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
Add-CMUserCollectionQueryMembershipRule -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -QueryExpression <String> -RuleName <String> [-ValidateQueryHasResult] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionQueryMembershipRule -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -QueryExpression <String> -RuleName <String> [-ValidateQueryHasResult] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionQueryMembershipRule [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] -QueryExpression <String> -RuleName <String> [-ValidateQueryHasResult] [-Confirm] [-WhatIf] [<CommonParameters>]
```
