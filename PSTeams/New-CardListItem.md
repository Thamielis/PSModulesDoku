New-CardListItem
----------------




### Synopsis

New-CardListItem [-Type] <string> [[-Icon] <string>] [[-Title] <string>] [[-SubTitle] <string>] [[-TapAction] <string>] [[-TapType] <string>] [[-TapValue] <string>] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Icon**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |1       |false        |



#### **SubTitle**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |3       |false        |



#### **TapAction**

Valid Values:

* whois
* editOnline






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |4       |false        |



#### **TapType**

Valid Values:

* imBack
* openUrl
* file






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |5       |false        |



#### **TapValue**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |6       |false        |



#### **Title**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |2       |false        |



#### **Type**

Valid Values:

* file
* resultItem
* section
* person






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |0       |false        |





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
{@{name=New-CardListItem; CommonParameters=True; parameter=System.Object[]}}
```
