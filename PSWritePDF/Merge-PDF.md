Merge-PDF
---------




### Synopsis
Merge PDF files into one.



---


### Description

Merge PDF files into one.



---


### Examples
#### EXAMPLE 1
```PowerShell
$FilePath1 = "$PSScriptRoot\Input\OutputDocument0.pdf"
$FilePath2 = "$PSScriptRoot\Input\OutputDocument1.pdf"
```
$OutputFile = "$PSScriptRoot\Output\OutputDocument.pdf" # Shouldn't exist / will be overwritten

Merge-PDF -InputFile $FilePath1, $FilePath2 -OutputFile $OutputFile


---


### Parameters
#### **InputFile**

The PDF files to be merged.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |1       |false        |



#### **OutputFile**

The output file path.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |



#### **IgnoreProtection**

The switch will allow reading of PDF files that are "owner password" encrypted for protection/security (e.g. preventing copying of text, printing etc).
The switch doesn't allow reading of PDF files that are "user password" encrypted (i.e. you cannot open them without the password)






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Merge-PDF [[-InputFile] <String[]>] [[-OutputFile] <String>] [-IgnoreProtection] [<CommonParameters>]
```
