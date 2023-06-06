New-AdaptiveColumnSet
---------------------




### Synopsis

New-AdaptiveColumnSet [[-Columns] <scriptblock>] [[-Style] <string>] [[-MinimumHeight] <int>] [[-Spacing] <string>] [[-HorizontalAlignment] <string>] [[-Height] <string>] [-Bleed] [-Separator] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Bleed**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Columns**




|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[scriptblock]`|false   |0       |false        |



#### **Height**

Valid Values:

* Stretch
* Automatic






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |5       |false        |



#### **HorizontalAlignment**

Valid Values:

* Left
* Center
* Right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |4       |false        |



#### **MinimumHeight**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|false   |2       |false        |



#### **Separator**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Spacing**

Valid Values:

* None
* Small
* Default
* Medium
* Large
* ExtraLarge
* Padding






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |3       |false        |



#### **Style**

Valid Values:

* Accent
* Default
* Emphasis
* Good
* Warning
* Attention






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |1       |false        |





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
{@{name=New-AdaptiveColumnSet; CommonParameters=True; parameter=System.Object[]}}
```
