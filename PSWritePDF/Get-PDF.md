Get-PDF
-------




### Synopsis
Gets PDF file and returns it as an PDF object



---


### Description

Gets PDF file and returns it as an PDF object



---


### Examples
#### EXAMPLE 1
```PowerShell
$Document = Get-PDF -FilePath "C:\Users\przemyslaw.klys\OneDrive - Evotec\Support\GitHub\PSWritePDF\Example\Example01.HelloWorld\Example01_WithSectionsMix.pdf"
$Details = Get-PDFDetails -Document $Document
$Details | Format-List
$Details.Pages | Format-Table
```
Close-PDF -Document $Document


---


### Parameters
#### **FilePath**

Path to the PDF file to be processed






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |1       |false        |



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
Get-PDF [[-FilePath] <String>] [-IgnoreProtection] [<CommonParameters>]
```
