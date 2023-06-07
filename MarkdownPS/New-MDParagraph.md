New-MDParagraph
---------------




### Synopsis
This commandlet output paragraph in markdown syntax



---


### Description

This commandlet output paragraph in markdown syntax



---


### Related Links
* [New-MDHeader
https://help.github.com/articles/basic-writing-and-formatting-syntax/](New-MDHeader
https://help.github.com/articles/basic-writing-and-formatting-syntax/)





---


### Examples
#### EXAMPLE 1
```PowerShell
New-MDParagraph
```
An empty line
#### EXAMPLE 2
```PowerShell
New-MDParagraph -Lines "Line 1"
"Line 1" | New-MDParagraph
```
Line 1
#### EXAMPLE 3
```PowerShell
New-MDParagraph -Lines @("Line 1","Line 2")
@("Line 1","Line 2") | New-MDParagraph
```
Line 1
Line 2


---


### Parameters
#### **Lines**

An array of lines to paragraph in markdown






|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[String[]]`|false   |1       |true (ByValue)|



#### **NoNewLine**

Controls if a new line is added at the end of the output






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Inputs
An array of lines



---


### Outputs
* Each line






---


### Notes
Use the -NoNewLine parameter when you don't want the next markdown content to be separated.



---


### Syntax
```PowerShell
New-MDParagraph [[-Lines] <String[]>] [-NoNewLine] [<CommonParameters>]
```
