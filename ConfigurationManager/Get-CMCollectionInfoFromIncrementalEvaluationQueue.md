Get-CMCollectionInfoFromIncrementalEvaluationQueue
--------------------------------------------------




### Synopsis
Get collection information from the incremental evaluation queue.



---


### Description

Get collection information from the incremental evaluation queue. For more information, see How to view collection evaluation (/mem/configmgr/core/clients/manage/collections/collection-evaluation-view).



> [!TIP] > The collection evaluation process happens on primary sites, not on the central administration site (CAS). Use this cmdlet when connected to a primary site.



---


### Related Links
* [Get-CMCollectionEvaluationStatus](Get-CMCollectionEvaluationStatus)



* [Get-CMCollectionFullEvaluationStatus](Get-CMCollectionFullEvaluationStatus)



* [Get-CMCollectionIncrementalEvaluationStatus](Get-CMCollectionIncrementalEvaluationStatus)



* [Get-CMCollectionInfoFromEvaluationQueue](Get-CMCollectionInfoFromEvaluationQueue)



* [Get-CMCollectionInfoFromFullEvaluationQueue](Get-CMCollectionInfoFromFullEvaluationQueue)



* [Get-CMCollectionInfoFromManualEvaluationQueue](Get-CMCollectionInfoFromManualEvaluationQueue)



* [Get-CMCollectionInfoFromNewEvaluationQueue](Get-CMCollectionInfoFromNewEvaluationQueue)



* [How to view collection evaluation](How to view collection evaluation)



* [Collection evaluation in Configuration Manager](Collection evaluation in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Get-CMCollectionInfoFromIncrementalEvaluationQueue -Id "SMS00002"
```



---


### Parameters
#### **Id**

Specify the ID of a collection to query. For example, `"SMS00002"`.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CollectionId|



#### **InputObject**

Specify a collection object to query. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases   |
|-----------------|--------|--------|-------------|----------|
|`[IResultObject]`|true    |named   |False        |Collection|



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
Get-CMCollectionInfoFromIncrementalEvaluationQueue -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionInfoFromIncrementalEvaluationQueue -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionInfoFromIncrementalEvaluationQueue [-Name <String>] [<CommonParameters>]
```
