Get-CMUserCollectionExcludeMembershipRule
-----------------------------------------




### Synopsis
Get an exclude membership rule for a user collection.



---


### Description

Use this cmdlet to get one or more exclude membership rules for a user collection. An exclude membership rule excludes the members of another collection from the user collections where the rule is applied.



Configuration Manager dynamically updates the membership of the user collection on a schedule if the membership of the excluded collection changes.



For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMUserCollectionExcludeMembershipRule](Add-CMUserCollectionExcludeMembershipRule)



* [Remove-CMUserCollectionExcludeMembershipRule](Remove-CMUserCollectionExcludeMembershipRule)



* [Get-CMCollectionExcludeMembershipRule](Get-CMCollectionExcludeMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Get-CMDeviceCollectionExcludeMembershipRule](Get-CMDeviceCollectionExcludeMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Get the exclude membership rules for a user collection
```PowerShell
Get-CMUserCollectionExcludeMembershipRule -CollectionId "XYZ00012" -ExcludeCollectionId "XYZ00089"
```



---


### Parameters
#### **CollectionId**

Specify the ID of the user collection to get the rule. This value is the CollectionID property, for example, `XYZ00012`. Since default collections don't have exclude membership rules, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the user collection to get the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **ExcludeCollection**

Specify an object for the excluded collection to get the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **ExcludeCollectionId**

Specify the ID of the excluded collection to get the rule. This value is the CollectionID property, for example, `XYZ00012`. You can exclude default collections, so this value can start with either the site code or `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ExcludeCollectionName**

Specify the name of the excluded collection to get the rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InputObject**

Specify an object for the user collection to get the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|





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
Get-CMUserCollectionExcludeMembershipRule -CollectionId <String> -ExcludeCollection <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionExcludeMembershipRule -CollectionId <String> -ExcludeCollectionId <String> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionExcludeMembershipRule -CollectionId <String> [-ExcludeCollectionName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionExcludeMembershipRule -CollectionName <String> [-ExcludeCollectionName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionExcludeMembershipRule -CollectionName <String> -ExcludeCollection <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionExcludeMembershipRule -CollectionName <String> -ExcludeCollectionId <String> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionExcludeMembershipRule -ExcludeCollection <IResultObject> -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionExcludeMembershipRule -ExcludeCollectionId <String> -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollectionExcludeMembershipRule [-ExcludeCollectionName <String>] -InputObject <IResultObject> [<CommonParameters>]
```
