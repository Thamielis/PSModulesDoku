Get-CMUserCollectionDirectMembershipRule
----------------------------------------




### Synopsis
Get a direct membership rule for a user collection.



---


### Description

Use this cmdlet to get one or more direct membership rules for a user collection. A direct membership rule lets you explicitly choose the members of the user collection. Default collections don't have direct membership rules. Any collection that you target should have an ID that starts with the site code, not `SMS`. For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMUserCollectionDirectMembershipRule](Add-CMUserCollectionDirectMembershipRule)



* [Remove-CMUserCollectionDirectMembershipRule](Remove-CMUserCollectionDirectMembershipRule)



* [Get-CMCollectionDirectMembershipRule](Get-CMCollectionDirectMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Get-CMResource](Get-CMResource)



* [Get-CMUser](Get-CMUser)



* [Get-CMDeviceCollectionDirectMembershipRule](Get-CMDeviceCollectionDirectMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Get all direct membership rules for a collection by name
```PowerShell
Get-CMUserCollectionDirectMembershipRule -CollectionName "Users"
```



---


### Parameters
#### **CollectionId**

Specify the ID of the user collection to get the rule. This value is the CollectionID property, for example, `XYZ00012`. Since default collections can't have direct membership rules, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the user collection to get the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **InputObject**

Specify an object for the user collection to get the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **Resource**

Specify a user object to get its direct membership rule from the user collection. To get this object, use the Get-CMResource (Get-CMResource.md) or [Get-CMUser](Get-CMUser.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **ResourceId**

Specify the ID of the user to get its direct membership rule from the user collection. This value is the ResourceID property, for example `16777219`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ResourceName**

Specify the name of the user to get its direct membership rule from the user collection.






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
Get-CMUserCollectionDirectMembershipRule -CollectionId <String> -Resource <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionDirectMembershipRule -CollectionId <String> -ResourceId <String> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionDirectMembershipRule -CollectionId <String> [-ResourceName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionDirectMembershipRule -CollectionName <String> [-ResourceName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionDirectMembershipRule -CollectionName <String> -Resource <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionDirectMembershipRule -CollectionName <String> -ResourceId <String> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionDirectMembershipRule -InputObject <IResultObject> -Resource <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionDirectMembershipRule -InputObject <IResultObject> -ResourceId <String> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionDirectMembershipRule -InputObject <IResultObject> [-ResourceName <String>] [<CommonParameters>]
```
