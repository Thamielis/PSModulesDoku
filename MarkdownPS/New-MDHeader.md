New-MDHeader
------------




### Synopsis
This commandlet output header in markdown syntax



---


### Description

This commandlet output header in markdown syntax by adding a '# '



---


### Related Links
* [New-MDParagraph
https://help.github.com/articles/basic-writing-and-formatting-syntax/](New-MDParagraph
https://help.github.com/articles/basic-writing-and-formatting-syntax/)





---


### Examples
#### EXAMPLE 1
```PowerShell
New-MDHeader -Text "This is an H1"
"This is an H1" | New-MDHeader -Text
```
# This is an H1
#### EXAMPLE 2
```PowerShell
New-MDHeader -Text "This is an H2" -Level 2
"This is an H2" | New-MDHeader -Text -Level 2
```
## This is an H2


---


### Parameters
#### **Text**

Any text






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[String]`|true    |1       |true (ByValue)|



#### **Level**

The level of header






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |false        |



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
* Each line with a '# ' in the front






---


### Notes
Use the -NoNewLine parameter when you don't want the next markdown content to be separated.



---


### Syntax
```PowerShell
New-MDHeader [-Text] <String> [-Level <Int32>] [-NoNewLine] [<CommonParameters>]
```
