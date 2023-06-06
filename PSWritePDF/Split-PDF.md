Split-PDF
---------




### Synopsis
Split PDF file into multiple files.



---


### Description

Split PDF file into multiple files. The output files will be named based on OutputName variable with appended numbers



---


### Examples
#### EXAMPLE 1
```PowerShell
Split-PDF -FilePath "$PSScriptRoot\SampleToSplit.pdf" -OutputFolder "$PSScriptRoot\Output"
```

#### EXAMPLE 2
```PowerShell
Split-PDF -FilePath "\\ad1\c$\SampleToSplit.pdf" -OutputFolder "\\ad1\c$\Output"
```



---


### Parameters
#### **FilePath**

The path to the PDF file to split.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **OutputFolder**

The folder to output the split files to.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |2       |false        |



#### **OutputName**

The name of the output files. Default is OutputDocument






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |3       |false        |



#### **SplitCount**

The number of pages to split the PDF file into. Default is 1






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |4       |false        |



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
Split-PDF [-FilePath] <String> [-OutputFolder] <String> [[-OutputName] <String>] [[-SplitCount] <Int32>] [-IgnoreProtection] [<CommonParameters>]
```
