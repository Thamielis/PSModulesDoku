New-MDCode
----------




### Synopsis
This commandlet output code block in markdown syntax



---


### Description

This commandlet output code blocke in markdown syntax by wrapping around ```



---


### Related Links
* [New-MDQuote
https://help.github.com/articles/basic-writing-and-formatting-syntax/](New-MDQuote
https://help.github.com/articles/basic-writing-and-formatting-syntax/)





---


### Examples
#### EXAMPLE 1
```PowerShell
New-MDCode -Lines "Line 1"
"Line 1" | New-MDCode
```
```
    Line 1
```
#### EXAMPLE 2
```PowerShell
New-MDCode -Lines @("Line 1","Line 2")
@("Line 1","Line 2") | New-MDCode
```
```
    Line 1
    Line 2
```
#### EXAMPLE 3
```PowerShell
New-MDCode -Lines @("Line 1","Line 2") -Style "powershell"
@("Line 1","Line 2") | New-MDCode -Style "powershell"
```
```powershell
    Line 1
    Line 2
```


---


### Parameters
#### **Lines**

An array of lines to code block in markdown






|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[String[]]`|true    |1       |true (ByValue)|



#### **Style**

The style of code. e.g. powershell or xml or javascript






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |





---


### Inputs
An array of lines



---


### Outputs
* Input wrapped in ```






---


### Syntax
```PowerShell
New-MDCode [-Lines] <String[]> [-Style <String>] [<CommonParameters>]
```
