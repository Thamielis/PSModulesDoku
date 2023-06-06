New-SpectreRule
---------------




### Synopsis

New-SpectreRule [[-Text] <array>] [[-Color] <array>] [[-Align] <Justify>] [[-RuleStyle] <string>] [[-RuleColor] <string>] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Align**

Valid Values:

* Left
* Right
* Center






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Justify]`|false   |2       |false        |



#### **Color**




|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[array]`|false   |1       |false        |



#### **RuleColor**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |4       |false        |



#### **RuleStyle**

Valid Values:

* bold
* dim
* italic
* underline
* invert
* conceal
* slowblink
* rapidblink
* strikethrough






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |3       |false        |



#### **Text**




|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[array]`|false   |0       |false        |





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
{@{name=New-SpectreRule; CommonParameters=True; parameter=System.Object[]}}
```
