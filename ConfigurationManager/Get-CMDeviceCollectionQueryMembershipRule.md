Get-CMDeviceCollectionQueryMembershipRule
-----------------------------------------




### Synopsis
Get a query membership rule for a device collection.



---


### Description

Use this cmdlet to get one or more query membership rules for a device collection. A query rule lets you dynamically update the membership of a collection based on a query that is run on a schedule. For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



For more information about membership rules, see Introduction to collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/introduction-to-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeviceCollectionQueryMembershipRule](Add-CMDeviceCollectionQueryMembershipRule)



* [Remove-CMDeviceCollectionQueryMembershipRule](Remove-CMDeviceCollectionQueryMembershipRule)



* [Get-CMCollectionQueryMembershipRule](Get-CMCollectionQueryMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMUserCollectionQueryMembershipRule](Get-CMUserCollectionQueryMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Get all query membership rules for the All Systems collection
```PowerShell
Get-CMDeviceCollectionQueryMembershipRule -CollectionName "All Systems"
```

#### Example 2: View the query expression for a rule on the All Systems collection
```PowerShell
Get-CMDeviceCollectionQueryMembershipRule -CollectionId "SMS00001" -RuleName "All Systems" | Select-Object QueryExpression
```



---


### Parameters
#### **CollectionId**

Specify the ID of the device collection to get the rule. This value is the CollectionID property, for example, `XYZ00012` or `SMS00001`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the device collection to get the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **InputObject**

Specify an object for the device collection to get the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






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




---


### Syntax
```PowerShell
Get-CMDeviceCollectionQueryMembershipRule -CollectionId <String> [-RuleName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionQueryMembershipRule -CollectionName <String> [-RuleName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionQueryMembershipRule -InputObject <IResultObject> [-RuleName <String>] [<CommonParameters>]
```
