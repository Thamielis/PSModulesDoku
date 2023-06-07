New-MDQuote
-----------




### Synopsis
This commandlet output quote in markdown syntax



---


### Description

This commandlet output quote in markdown syntax by adding a '> ' in front of each line



---


### Related Links
* [New-MDCode
https://help.github.com/articles/basic-writing-and-formatting-syntax/](New-MDCode
https://help.github.com/articles/basic-writing-and-formatting-syntax/)





---


### Examples
#### EXAMPLE 1
```PowerShell
New-MDQuote -Lines "Line 1"
```
> Line 1
#### EXAMPLE 2
```PowerShell
New-MDQuote -Lines @("Line 1","Line 2")
```
> Line 1
> 
> Line 2
#### EXAMPLE 3
```PowerShell
@("Line 1","Line 2") | New-MDQuote -Level 2
```
>> Line 1
>>
>> Line 2


---


### Parameters
#### **Lines**

An array of lines to quote in markdown






|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[String[]]`|true    |1       |true (ByValue)|



#### **Level**

The level of quote






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
* Each line with a '> ' in the front






---


### Notes
Use the -NoNewLine parameter when you don't want the next markdown content to be separated.



---


### Syntax
```PowerShell
New-MDQuote [-Lines] <String[]> [-Level <Int32>] [-NoNewLine] [<CommonParameters>]
```
