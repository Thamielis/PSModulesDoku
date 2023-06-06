New-AdaptiveColumn
------------------




### Synopsis

New-AdaptiveColumn [[-Items] <scriptblock>] [[-Spacing] <string>] [[-Height] <string>] [[-Width] <string>] [[-WidthInWeight] <int>] [[-WidthInPixels] <int>] [[-MinimumHeight] <int>] [[-HorizontalAlignment] <string>] [[-VerticalContentAlignment] <string>] [[-Style] <string>] [[-SelectAction] <string>] [[-SelectActionId] <string>] [[-SelectActionUrl] <string>] [[-SelectActionTitle] <string>] [[-SelectActionTargetElement] <string[]>] [-Hidden] [-Separator] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Height**

Valid Values:

* Stretch
* Automatic






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |2       |false        |



#### **Hidden**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **HorizontalAlignment**

Valid Values:

* Left
* Center
* Right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |7       |false        |



#### **Items**




|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[scriptblock]`|false   |0       |false        |



#### **MinimumHeight**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|false   |6       |false        |



#### **SelectAction**

Valid Values:

* Action.Submit
* Action.OpenUrl
* Action.ToggleVisibility






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |10      |false        |



#### **SelectActionId**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |11      |false        |



#### **SelectActionTargetElement**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|false   |14      |false        |



#### **SelectActionTitle**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |13      |false        |



#### **SelectActionUrl**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |12      |false        |



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
|`[string]`|false   |1       |false        |



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
|`[string]`|false   |9       |false        |



#### **VerticalContentAlignment**

Valid Values:

* Top
* Center
* Bottom






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |8       |false        |



#### **Width**

Valid Values:

* Stretch
* Auto
* Weighted






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |3       |false        |



#### **WidthInPixels**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|false   |5       |false        |



#### **WidthInWeight**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|false   |4       |false        |





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
{@{name=New-AdaptiveColumn; CommonParameters=True; parameter=System.Object[]}}
```
