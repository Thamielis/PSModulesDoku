New-AdaptiveContainer
---------------------




### Synopsis

New-AdaptiveContainer [[-Items] <scriptblock>] [[-Spacing] <string>] [[-HorizontalAlignment] <string>] [[-Height] <string>] [[-Style] <string>] [[-MinimumHeight] <int>] [[-VerticalContentAlignment] <string>] [[-Id] <string>] [[-BackgroundUrl] <string>] [[-BackgroundFillMode] <string>] [[-BackgroundHorizontalAlignment] <string>] [[-BackgroundVerticalAlignment] <string>] [[-SelectAction] <string>] [[-SelectActionId] <string>] [[-SelectActionUrl] <string>] [[-SelectActionTitle] <string>] [[-SelectActionTargetElement] <string[]>] [-Separator] [-Bleed] [-Hidden] [<CommonParameters>]




---


### Description


---


### Parameters
#### **BackgroundFillMode**

Valid Values:

* Cover
* RepeatHorizontally
* RepeatVertically
* Repeat






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |9       |false        |



#### **BackgroundHorizontalAlignment**

Valid Values:

* left
* center
* right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |10      |false        |



#### **BackgroundUrl**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |8       |false        |



#### **BackgroundVerticalAlignment**

Valid Values:

* top
* center
* bottom






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |11      |false        |



#### **Bleed**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Height**

Valid Values:

* Stretch
* Automatic






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |3       |false        |



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
|`[string]`|false   |2       |false        |



#### **Id**




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
|`[int]`|false   |5       |false        |



#### **SelectAction**

Valid Values:

* Action.Submit
* Action.OpenUrl
* Action.ToggleVisibility






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |12      |false        |



#### **SelectActionId**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |13      |false        |



#### **SelectActionTargetElement**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|false   |16      |false        |



#### **SelectActionTitle**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |15      |false        |



#### **SelectActionUrl**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |14      |false        |



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
|`[string]`|false   |4       |false        |



#### **VerticalContentAlignment**

Valid Values:

* top
* center
* bottom






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |6       |false        |





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
{@{name=New-AdaptiveContainer; CommonParameters=True; parameter=System.Object[]}}
```
