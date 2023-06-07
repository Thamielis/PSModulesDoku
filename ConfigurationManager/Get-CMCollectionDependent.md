Get-CMCollectionDependent
-------------------------




### Synopsis
Get a collection's dependent relationships.



---


### Description

This cmdlet gets the target collection's dependent relationships. The target collection is a limiting collection for one or more other collections.



For more information, see View collection relationships (/mem/configmgr/core/clients/manage/collections/manage-collections#view-collection-relationships).



---


### Related Links
* [Get-CMCollectionDependency](Get-CMCollectionDependency)



* [View collection relationships](View collection relationships)





---


### Examples
#### Example 1: Get the collection relationships by pipeline object
```PowerShell
Get-CMCollection -Name "All Users" | Get-CMCollectionDependent
```

#### Example 2: Get the collection relationships by ID
```PowerShell
Get-CMCollectionDependent -Id "SMS00002"
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
Get-CMCollectionDependent [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDependent [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDependent [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
