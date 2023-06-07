New-MDTable
-----------




### Synopsis
This commandlet output a table in markdown syntax



---


### Description

This commandlet output quote in markdown syntax by adding a two rows for the header and then one line per entry in the array.



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-Command New-MDTable |Select-Object Name,CommandType | New-MDTable
```
| Name        | CommandType |
| ----------- | ----------- |
| New-MDTable | Function    |
#### EXAMPLE 2
```PowerShell
Get-Command New-MDTable |Select-Object Name,CommandType | New-MDTable -Shrink
```
| Name | CommandType |
| ---- | ----------- |
| New-MDTable | Function |
#### EXAMPLE 3
```PowerShell
Get-Command New-MDTable | New-MDTable -Columns ([ordered]@{Name=$null;CommandType=$null})
```
| Name        | CommandType |
| ----------- | ----------- |
| New-MDTable | Function    |
#### EXAMPLE 4
```PowerShell
Get-Command New-MDTable | New-MDTable -Columns ([ordered]@{CommandType=$null;Name=$null})
```
| CommandType | Name        |
| ----------- | ----------- |
| Function    | New-MDTable |
#### EXAMPLE 5
```PowerShell
Get-Command New-MDTable | New-MDTable -Columns (@{CommandType=$null;Name=$null})
```
| Name        | CommandType |
| ----------- | ----------- |
| New-MDTable | Function    |
#### EXAMPLE 6
```PowerShell
Get-Command New-MDTable | New-MDTable -Columns ([ordered]@{Name="left";CommandType="center";Version="right"})
| Name        | CommandType | Version     |
| ----------- |:-----------:| -----------:|
| New-MDTable | Function    |             |
```



---


### Parameters
#### **Object**

Any object






|Type          |Required|Position|PipelineInput |
|--------------|--------|--------|--------------|
|`[PSObject[]]`|true    |1       |true (ByValue)|



#### **Columns**

The columns that compose the table. Columns must be an ordered hashtable [ordered]@{} where the keys are the column names and as optional value (left,center,right).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |named   |false        |



#### **NoNewLine**

Controls if a new line is added at the end of the output






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **Shrink**

Shrinks each row to just actually fill the data






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Inputs
Any table



---


### Outputs
* A table representation in markdown






---


### Notes
Use the -NoNewLine parameter when you don't want the next markdown content to be separated.



---


### Syntax
```PowerShell
New-MDTable [-Object] <PSObject[]> [-Columns <Object>] [-NoNewLine] [-Shrink] [<CommonParameters>]
```
