Set-PDFForm
-----------




### Synopsis
Will try to fill form fields in source PDF with values from hash table.
Can also flatten the form to prevent changes with -flatten.



---


### Description

Adds a file name extension to a supplied name.
Takes any strings for the file name or extension.



---


### Examples
#### EXAMPLE 1
```PowerShell
$FilePath = [IO.Path]::Combine("$PSScriptRoot", "Output", "SampleAcroFormOutput.pdf")
$FilePathSource = [IO.Path]::Combine("$PSScriptRoot", "Input", "SampleAcroForm.pdf")
```
$FieldNameAndValueHashTable = [ordered] @{
    "Text 1" = "Text 1 input"
    "Text 2" = "Text 2 input"
    "Text 3" = "Text 3 input"
    "Check Box 1 True" = $true
    "Check Box 2 False" = $false
    "Check Box 3 False" = $false
    "Check Box 4 True" = $true
    "Doesn't Exist" = "will not be used"
}
Set-PDFForm -SourceFilePath $FilePathSource -DestinationFilePath $FilePath -FieldNameAndValueHashTable $FieldNameAndValueHashTable -Flatten
#### EXAMPLE 2
```PowerShell
$FilePath = [IO.Path]::Combine("$PSScriptRoot", "Output", "SampleAcroFormOutput.pdf")
$FilePathSource = [IO.Path]::Combine("$PSScriptRoot", "Input", "SampleAcroForm.pdf")
Set-PDFForm -SourceFilePath $FilePathSource -DestinationFilePath $FilePath -Flatten
```



---


### Parameters
#### **SourceFilePath**

Specifies the to be filled in PDF Form.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **DestinationFilePath**

Specifies the output filepath for the completed form.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |2       |false        |



#### **FieldNameAndValueHashTable**

Specifies the hashtable for the fields data. Key in the hashtable needs to match the feild name in the PDF.






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[IDictionary]`|false   |3       |false        |



#### **Flatten**

Will flatten the output PDF so form fields will no longer be able to be changed.






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[Switch]`|false   |named   |false        |FlattenFields|



#### **IgnoreProtection**

The switch will allow reading of PDF files that are "owner password" encrypted for protection/security (e.g. preventing copying of text, printing etc).
The switch doesn't allow reading of PDF files that are "user password" encrypted (i.e. you cannot open them without the password)






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Syntax
```PowerShell
Set-PDFForm [-SourceFilePath] <Object> [-DestinationFilePath] <Object> [[-FieldNameAndValueHashTable] <IDictionary>] [-Flatten] [-IgnoreProtection] [<CommonParameters>]
```
