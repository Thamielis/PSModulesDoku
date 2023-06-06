New-SpreadSheet
---------------




### Synopsis
Creates a new spreadsheet from a prompt



---


### Description

Creates a new spreadsheet from a prompt



---


### Examples
#### EXAMPLE 1
```PowerShell
.\New-Spreadsheet.ps1 "first 5 US presidents name, term, party"
```

#### EXAMPLE 2
```PowerShell
.\New-Spreadsheet.ps1 "first 5 US presidents name, term, party" -Raw
```



---


### Parameters
#### **prompt**

The prompt to use






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **Raw**

If set, returns the raw markdown table instead of converting it to an Excel spreadsheet






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Syntax
```PowerShell
New-SpreadSheet [-prompt] <Object> [-Raw] [<CommonParameters>]
```
