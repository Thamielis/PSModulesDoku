New-AdaptiveAction
------------------




### Synopsis

New-AdaptiveAction [[-Body] <scriptblock>] [[-Actions] <scriptblock>] [[-Type] <string>] [[-ActionUrl] <string>] [[-Title] <string>] [<CommonParameters>]




---


### Description


---


### Parameters
#### **ActionUrl**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |3       |false        |



#### **Actions**




|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[scriptblock]`|false   |1       |false        |



#### **Body**




|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[scriptblock]`|false   |0       |false        |



#### **Title**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |4       |false        |



#### **Type**

Valid Values:

* Action.ShowCard
* Action.Submit
* Action.OpenUrl
* Action.ToggleVisibility






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |2       |false        |





---


### Inputs
None




---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Syntax
```PowerShell
syntaxItem
```
```PowerShell
----------
```
```PowerShell
{@{name=New-AdaptiveAction; CommonParameters=True; parameter=System.Object[]}}
```
