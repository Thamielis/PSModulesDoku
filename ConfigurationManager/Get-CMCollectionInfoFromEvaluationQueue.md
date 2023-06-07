Get-CMCollectionInfoFromEvaluationQueue
---------------------------------------




### Synopsis
Get collection information from the evaluation queue.



---


### Description

Get collection information from the evaluation queue. For more information, see How to view collection evaluation (/mem/configmgr/core/clients/manage/collections/collection-evaluation-view).



> [!TIP] > The collection evaluation process happens on primary sites, not on the central administration site (CAS). Use this cmdlet when connected to a primary site.



---


### Related Links
* [Get-CMCollectionEvaluationStatus](Get-CMCollectionEvaluationStatus)



* [Get-CMCollectionFullEvaluationStatus](Get-CMCollectionFullEvaluationStatus)



* [Get-CMCollectionIncrementalEvaluationStatus](Get-CMCollectionIncrementalEvaluationStatus)



* [Get-CMCollectionInfoFromFullEvaluationQueue](Get-CMCollectionInfoFromFullEvaluationQueue)



* [Get-CMCollectionInfoFromIncrementalEvaluationQueue](Get-CMCollectionInfoFromIncrementalEvaluationQueue)



* [Get-CMCollectionInfoFromManualEvaluationQueue](Get-CMCollectionInfoFromManualEvaluationQueue)



* [Get-CMCollectionInfoFromNewEvaluationQueue](Get-CMCollectionInfoFromNewEvaluationQueue)



* [How to view collection evaluation](How to view collection evaluation)



* [Collection evaluation in Configuration Manager](Collection evaluation in Configuration Manager)





---


### Examples
#### Example 1: Show all collections due for full evaluation
```PowerShell
Get-CMCollectionInfoFromEvaluationQueue -EvaluationTypeOption Full
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EvaluationTypeOption**

Specify the type of evaluation queue for which to get the status. For more information, see Monitoring collection evaluation queues (/mem/configmgr/core/clients/manage/collections/collection-evaluation-view#monitoring-collection-evaluation-queues).



Valid Values:

* Full
* Incremental
* Manual
* New






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[EvaluationType]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of a collection to query. For example, `"SMS00002"`.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |0       |False        |CollectionId|



#### **InputObject**

Specify a collection object to query. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |0       |True (ByValue)|Collection|



#### **Name**

Specify the name of a collection to query. For example, `"All Users"`.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |0       |False        |CollectionName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_CollectionInfoInFullEvaluationQueue


* IResultObject#SMS_CollectionInfoInFullEvaluationQueue


* IResultObject[]#SMS_CollectionInfoInIncrementalEvaluationQueue


* IResultObject#SMS_CollectionInfoInIncrementalEvaluationQueue


* IResultObject[]#SMS_CollectionInfoInManualEvaluationQueue


* IResultObject#SMS_CollectionInfoInManualEvaluationQueue


* IResultObject[]#SMS_CollectionInfoInNewEvaluationQueue


* IResultObject#SMS_CollectionInfoInNewEvaluationQueue






---


### Notes




---


### Syntax
```PowerShell
Get-CMCollectionInfoFromEvaluationQueue [-Id] <String> [-DisableWildcardHandling] -EvaluationTypeOption {Full | Incremental | Manual | New} [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionInfoFromEvaluationQueue [-InputObject] <IResultObject> [-DisableWildcardHandling] -EvaluationTypeOption {Full | Incremental | Manual | New} [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionInfoFromEvaluationQueue [[-Name] <String>] [-DisableWildcardHandling] -EvaluationTypeOption {Full | Incremental | Manual | New} [-ForceWildcardHandling] [<CommonParameters>]
```
