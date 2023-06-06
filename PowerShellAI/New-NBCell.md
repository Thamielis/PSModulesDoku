New-NBCell
----------




### Synopsis
Creates a new cell in a Polyglot Interactive Notebook



---


### Description

Creates a new cell in a Polyglot Interactive Notebook
This is a helper function for the other functions in this module
It is not intended to be used directly



---


### Examples
#### EXAMPLE 1
```PowerShell
New-NBCell -cellType 'pwsh' -code 'Get-Process'
```



---


### Parameters
#### **cellType**

Valid Values:

* pwsh
* csharp
* fsharp
* html
* markdown
* javascript
* sql
* mermaid
* kql






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |1       |false        |



#### **code**




|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[Object]`|false   |2       |true (ByValue)|





---


### Syntax
```PowerShell
New-NBCell [[-cellType] <Object>] [[-code] <Object>] [<CommonParameters>]
```
