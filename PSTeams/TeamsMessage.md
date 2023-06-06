Send-TeamsMessage
-----------------




### Synopsis

Send-TeamsMessage [[-SectionsInput] <scriptblock>] [-Uri] <string> [[-MessageTitle] <string>] [[-MessageText] <string>] [[-MessageSummary] <string>] [[-Color] <string>] [[-Proxy] <uri>] [[-Sections] <IDictionary[]>] [[-Suppress] <bool>] [-HideOriginalBody] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Color**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |5       |false        |



#### **HideOriginalBody**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **MessageSummary**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |4       |false        |



#### **MessageText**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |3       |false        |



#### **MessageTitle**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |2       |false        |



#### **Proxy**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[uri]`|false   |6       |false        |



#### **Sections**




|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IDictionary[]]`|false   |7       |false        |



#### **SectionsInput**




|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[scriptblock]`|false   |0       |false        |



#### **Suppress**




|Type    |Required|Position|PipelineInput|Aliases|
|--------|--------|--------|-------------|-------|
|`[bool]`|false   |8       |false        |Supress|



#### **Uri**




|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[string]`|true    |1       |false        |TeamsID<br/>Url|





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
{@{name=Send-TeamsMessage; CommonParameters=True; parameter=System.Object[]}}
```
