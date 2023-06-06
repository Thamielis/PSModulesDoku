Convert-PDFToText
-----------------




### Synopsis
Converts PDF to TEXT



---


### Description

Converts PDF to TEXT



---


### Examples
#### EXAMPLE 1
```PowerShell
# Get all pages text
Convert-PDFToText -FilePath "$PSScriptRoot\Example04.pdf"
```

#### EXAMPLE 2
```PowerShell
# Get all pages text with Location-Extractionstrategy
Convert-PDFToText -FilePath "$PSScriptRoot\Example04.pdf" -ExtractionStrategy "LT"
```

#### EXAMPLE 3
```PowerShell
# Get page 1 text only
Convert-PDFToText -FilePath "$PSScriptRoot\Example04.pdf" -Page 1
```



---


### Parameters
#### **FilePath**

The path to the PDF file to convert






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |1       |false        |



#### **Page**

The page number to convert (default is all pages)






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Int32[]]`|false   |2       |false        |



#### **ExtractionStrategy**

The iText Extractiostrategey that is used to parse the text. Currently supports LocationTextExtractionStrategy (LT) and SimpleTextExtractionStrategy (ST)(Default).



Valid Values:

* SimpleTextExtractionStrategy
* LocationTextExtractionStrategy
* ST
* LT






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |3       |false        |



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
Convert-PDFToText [[-FilePath] <String>] [[-Page] <Int32[]>] [[-ExtractionStrategy] <String>] [-IgnoreProtection] [<CommonParameters>]
```
