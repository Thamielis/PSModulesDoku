Get-CMCollectionQueryMembershipRule
-----------------------------------




### Synopsis
Get a query membership rule for a device or user collection.



---


### Description

Use this cmdlet to get one or more query membership rules for a device or user collection. A query rule lets you dynamically update the membership of a collection based on a query that is run on a schedule. For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



For more information about membership rules, see Introduction to collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/introduction-to-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMCollectionQueryMembershipRule](Remove-CMCollectionQueryMembershipRule)



* [Get-CMCollectionDirectMembershipRule](Get-CMCollectionDirectMembershipRule)



* [Get-CMCollectionExcludeMembershipRule](Get-CMCollectionExcludeMembershipRule)



* [Get-CMCollectionIncludeMembershipRule](Get-CMCollectionIncludeMembershipRule)



* [Add-CMDeviceCollectionQueryMembershipRule](Add-CMDeviceCollectionQueryMembershipRule)



* [Add-CMUserCollectionQueryMembershipRule](Add-CMUserCollectionQueryMembershipRule)



* [Get-CMDeviceCollectionQueryMembershipRule](Get-CMDeviceCollectionQueryMembershipRule)



* [Get-CMUserCollectionQueryMembershipRule](Get-CMUserCollectionQueryMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Get all query membership rules for the All Systems collection
```PowerShell
Get-CMCollectionQueryMembershipRule -CollectionName "All Systems"
```

#### Example 2: View the query expression for a rule on the All Users collection
```PowerShell
Get-CMCollectionQueryMembershipRule -CollectionId "SMS00002" -RuleName "All Users" | Select-Object QueryExpression
```



---


### Parameters
#### **CollectionId**

Specify the ID of the collection to get the rule. This value is the CollectionID property, for example, `XYZ00012` or `SMS00001`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the collection to get the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **InputObject**

Specify an object for the collection to get the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md), [Get-CMDeviceCollection](Get-CMDeviceCollection.md), or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **RuleName**

Specify the name of the query rule to get from the collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes
This cmdlet is similar to Get-CMDeviceCollectionQueryMembershipRule and Get-CMUserCollectionQueryMembershipRule , which are specific to the type of collection. This cmdlet works with either device or user collections.



---


### Syntax
```PowerShell
Get-CMCollectionQueryMembershipRule -CollectionId <String> [-RuleName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionQueryMembershipRule -CollectionName <String> [-RuleName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionQueryMembershipRule -InputObject <IResultObject> [-RuleName <String>] [<CommonParameters>]
```
