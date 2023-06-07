Get-CMCollectionDependency
--------------------------




### Synopsis
Get the limiting collection for the target collection.



---


### Description

This cmdlet gets the limiting collection for a Configuration Manager collection. Except for the All Systems and All Users and User Groups collections, all collections have a parent collection that limit their membership. The limiting collection establishes the resources that you can add to this collection with membership rules.



For more information, see View collection relationships (/mem/configmgr/core/clients/manage/collections/manage-collections#view-collection-relationships).



---


### Related Links
* [Get-CMCollectionDependent](Get-CMCollectionDependent)



* [View collection relationships](View collection relationships)





---


### Examples
#### Example 1: Get the limiting collection by pipeline object
```PowerShell
Get-CMCollection -Name "All Users" | Get-CMCollectionDependency
```

#### Example 2: Get the limiting collection by ID
```PowerShell
Get-CMCollectionDependency -Id "SMS00002"
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

Specify the ID of a collection to query. For example, `"SMS00002"`.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CollectionId|



#### **InputObject**

Specify a collection object to query. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **Name**

Specify a collection name to query. For example, `"All Users"`.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |CollectionName|





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
Get-CMCollectionDependency [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDependency [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDependency [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
