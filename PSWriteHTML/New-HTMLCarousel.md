New-HTMLCarousel
----------------




### Synopsis

New-HTMLCarousel [[-Slide] <scriptblock>] [[-Mode] <string>] [[-Align] <string>] [[-PerView] <Object>] [[-Height] <string>] [[-Margin] <string>] [[-StartAt] <int>] [-Loop] [-Pagination] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Align**

Valid Values:

* center
* start
* end
* justify






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |2       |false        |



#### **Height**

Valid Values:

* adaptive
* equal
* auto






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |4       |false        |



#### **Loop**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Margin**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |5       |false        |



#### **Mode**

Valid Values:

* Horizontal
* Vertical






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |1       |false        |



#### **Pagination**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **PerView**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |3       |false        |



#### **Slide**




|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[scriptblock]`|false   |0       |false        |



#### **StartAt**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|false   |6       |false        |





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
{@{name=New-HTMLCarousel; CommonParameters=True; parameter=System.Object[]}}
```
