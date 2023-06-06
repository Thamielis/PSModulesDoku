Convert-HTMLToPDF
-----------------




### Synopsis
Converts HTML to PDF.



---


### Description

Converts HTML to PDF from one of three sources:
1. A file on the local file system.
2. A URL.
3. A string of HTML.



---


### Examples
#### EXAMPLE 1
```PowerShell
Convert-HTMLToPDF -Uri 'https://evotec.xyz/hub/scripts/pswritehtml-powershell-module/' -OutputFilePath "$PSScriptRoot\Example10-FromURL.pdf" -Open
```

#### EXAMPLE 2
```PowerShell
$HTMLInput = New-HTML {
    New-HTMLText -Text 'Test 1'
    New-HTMLTable -DataTable (Get-Process | Select-Object -First 3)
}
```
Convert-HTMLToPDF -Content $HTMLInput -OutputFilePath "$PSScriptRoot\Example10-FromHTML.pdf" -Open
#### EXAMPLE 3
```PowerShell
New-HTML {
    New-HTMLTable -DataTable (Get-Process | Select-Object -First 3)
} -FilePath "$PSScriptRoot\Example10-FromFilePath.html" -Online
```
Convert-HTMLToPDF -FilePath "$PSScriptRoot\Example10-FromFilePath.html" -OutputFilePath "$PSScriptRoot\Example10-FromFilePath.pdf" -Open


---


### Parameters
#### **Uri**

The URI of the HTML to convert.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |false        |Url    |



#### **Content**

The HTML (as a string) to convert.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **FilePath**

The path to the file containing the HTML to convert.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **OutputFilePath**

The path to the file to write the PDF to.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **Open**

If true, opens the PDF after it is created.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Convert-HTMLToPDF -Uri <String> -OutputFilePath <String> [-Open] [<CommonParameters>]
```
```PowerShell
Convert-HTMLToPDF -Content <String> -OutputFilePath <String> [-Open] [<CommonParameters>]
```
```PowerShell
Convert-HTMLToPDF -FilePath <String> -OutputFilePath <String> [-Open] [<CommonParameters>]
```
