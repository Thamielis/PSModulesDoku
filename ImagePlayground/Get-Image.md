Get-Image
---------




### Synopsis
Gets the image from the file path for further processing and image manipulation.



---


### Description

Gets the image from the file path for further processing and image manipulation.



---


### Examples
#### EXAMPLE 1
```PowerShell
$Image = Get-Image -FilePath $PSScriptRoot\Samples\LogoEvotec.png
$Image.BlackWhite()
$Image.BackgroundColor("Red")
Save-Image -Image $Image -Open -FilePath $PSScriptRoot\Output\LogoEvotecChanged.png
```



---


### Parameters
#### **FilePath**

File path to the image you want to read and manipulate.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |1       |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Get-Image [[-FilePath] <String>] [<CommonParameters>]
```
