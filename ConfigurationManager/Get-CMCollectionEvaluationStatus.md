Get-CMCollectionEvaluationStatus
--------------------------------




### Synopsis
Get the status of collection evaluation.



---


### Description

Get the status of collection evaluation. For more information, see How to view collection evaluation (/mem/configmgr/core/clients/manage/collections/collection-evaluation-view).



> [!TIP] > The collection evaluation process happens on primary sites, not on the central administration site (CAS). Use this cmdlet when connected to a primary site.



---


### Related Links
* [Get-CMCollectionFullEvaluationStatus](Get-CMCollectionFullEvaluationStatus)



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
Get-CMCollectionEvaluationStatus -EvaluationTypeOption Full | Where-Object Length -gt 5000
```

#### Example 2: Show summary of full evaluation on built-in collections that recently changed
```PowerShell
Get-CMCollection -Name "All*" | Get-CMCollectionEvaluationStatus -EvaluationTypeOption Full -IsMemberChanged $True | Select-Object CollectionName, Length, MemberChanges
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EvaluationTypeOption**

Specify the type of evaluation for which to get the status, either `Full` or `Incremental`. For more information, see Collection evaluation in Configuration Manager (/mem/configmgr/core/clients/manage/collections/collection-evaluation).



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



#### **IsMemberChanged**

Set this parameter to `$true` to filter the results to collections whose membership recently changed. In other words, where the MemberChanges attribute isn't `0`.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* IResultObject[]#SMS_CollectionEvaluationFull


* IResultObject#SMS_CollectionEvaluationFull


* IResultObject[]#SMS_CollectionEvaluationIncremental


* IResultObject#SMS_CollectionEvaluationIncremental






---


### Notes




---


### Syntax
```PowerShell
Get-CMCollectionEvaluationStatus [-Id] <String> [-DisableWildcardHandling] -EvaluationTypeOption {Full | Incremental} [-ForceWildcardHandling] [-IsMemberChanged <Boolean>] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionEvaluationStatus [-InputObject] <IResultObject> [-DisableWildcardHandling] -EvaluationTypeOption {Full | Incremental} [-ForceWildcardHandling] [-IsMemberChanged <Boolean>] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionEvaluationStatus [[-Name] <String>] [-DisableWildcardHandling] -EvaluationTypeOption {Full | Incremental} [-ForceWildcardHandling] [-IsMemberChanged <Boolean>] [<CommonParameters>]
```
