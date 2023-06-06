New-TeamsButton
---------------




### Synopsis

New-TeamsButton [-Name] <string> [-Link] <string> [[-Type] <string>] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Link**




|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[string]`|true    |1       |false        |TargetUri<br/>Uri<br/>Url|



#### **Name**




|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[string]`|true    |0       |false        |ButtonName|



#### **Type**

Valid Values:

* ViewAction
* TextInput
* DateInput
* HttpPost
* OpenUri






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[string]`|false   |2       |false        |ButtonType|





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
{@{name=New-TeamsButton; CommonParameters=True; parameter=System.Object[]}}
```
