Get-CMCollectionFullEvaluationStatus
------------------------------------




### Synopsis
Get the full evaluation status for a collection.



---


### Description

Get the full evaluation status for a collection. For more information, see How to view collection evaluation (/mem/configmgr/core/clients/manage/collections/collection-evaluation-view).



> [!TIP] > The collection evaluation process happens on primary sites, not on the central administration site (CAS). Use this cmdlet when connected to a primary site.



---


### Related Links
* [Get-CMCollectionEvaluationStatus](Get-CMCollectionEvaluationStatus)



* [Get-CMCollectionIncrementalEvaluationStatus](Get-CMCollectionIncrementalEvaluationStatus)



* [Get-CMCollectionInfoFromEvaluationQueue](Get-CMCollectionInfoFromEvaluationQueue)



* [Get-CMCollectionInfoFromFullEvaluationQueue](Get-CMCollectionInfoFromFullEvaluationQueue)



* [Get-CMCollectionInfoFromIncrementalEvaluationQueue](Get-CMCollectionInfoFromIncrementalEvaluationQueue)



* [Get-CMCollectionInfoFromManualEvaluationQueue](Get-CMCollectionInfoFromManualEvaluationQueue)



* [Get-CMCollectionInfoFromNewEvaluationQueue](Get-CMCollectionInfoFromNewEvaluationQueue)



* [How to view collection evaluation](How to view collection evaluation)



* [Collection evaluation in Configuration Manager](Collection evaluation in Configuration Manager)





---


### Examples
#### Example 1: Show status for collections with long full evaluation
```PowerShell
Get-CMCollectionFullEvaluationStatus | Where-Object Length -gt 5000
```



---


### Parameters
#### **Id**

Specify the ID of a collection to query. For example, `"SMS00002"`.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CollectionId|



#### **InputObject**

Specify a collection object to query. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet. This parameter currently only accepts a single collection object.






|Type             |Required|Position|PipelineInput|Aliases   |
|-----------------|--------|--------|-------------|----------|
|`[IResultObject]`|true    |named   |False        |Collection|



#### **IsMemberChanged**

Set this parameter to `$true` to filter the results to collections whose membership recently changed. In other words, where the MemberChanges attribute isn't `0`.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify the name of a collection to query. For example, `"All Users"`.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |CollectionName|





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Get-CMCollectionFullEvaluationStatus -Id <String> [-IsMemberChanged <Boolean>] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionFullEvaluationStatus -InputObject <IResultObject> [-IsMemberChanged <Boolean>] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionFullEvaluationStatus [-IsMemberChanged <Boolean>] [-Name <String>] [<CommonParameters>]
```
