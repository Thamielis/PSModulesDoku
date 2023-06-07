New-MDList
----------




### Synopsis
This commandlet output list in markdown syntax



---


### Description

This commandlet output list in markdown syntax. Depending if the list is unordered or ordere, the '- ' or '1. ' is added in front of each line



---


### Related Links
* [New-MDParagraph
https://help.github.com/articles/basic-writing-and-formatting-syntax/](New-MDParagraph
https://help.github.com/articles/basic-writing-and-formatting-syntax/)





---


### Examples
#### EXAMPLE 1
```PowerShell
New-MDList -Lines "Line 1" -Style Unordered
"Line 1" | New-MDList -Style Unordered
```
- Line 1
#### EXAMPLE 2
```PowerShell
New-MDList -Lines @("Line 1","Line 2") -Style Unordered
@("Line 1","Line 2") | New-MDList -Style Unordered
```
- Line 1
- Line 2
#### EXAMPLE 3
```PowerShell
New-MDList -Lines "Line 1" -Style Ordered
"Line 1" | New-MDList -Style Ordered
```
1. Line 1
#### EXAMPLE 4
```PowerShell
New-MDList -Lines @("Line 1","Line 2") -Style Ordered
@("Line 1","Line 2") | New-MDList -Style Ordered
```
1. Line 1
2. Line 2


---


### Parameters
#### **Lines**

An array of lines to make a list in markdown






|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[String[]]`|true    |1       |true (ByValue)|



#### **Level**

The level of list






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |false        |



#### **Style**

The type of list. Ordered or Unordered



Valid Values:

* Unordered
* Ordered






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



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
* Each line with a '- ' or '1. ' in the front depending on the type of the list.






---


### Notes
Use the -NoNewLine parameter when you don't want the next markdown content to be separated.



---


### Syntax
```PowerShell
New-MDList [-Lines] <String[]> [-Level <Int32>] -Style <String> [-NoNewLine] [<CommonParameters>]
```
