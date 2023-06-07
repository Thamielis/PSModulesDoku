Save-Image
----------




### Synopsis
Saves image that was open for processing



---


### Description

Saves image that was open for processing



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
#### **Image**

Image object to be saved






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Image]`|true    |1       |false        |



#### **FilePath**

File path to where the image should be saved. If not specified, the original image will be overwritten.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |



#### **Open**

Opens the image in default image viewer after saving






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Save-Image [-Image] <Image> [[-FilePath] <String>] [-Open] [<CommonParameters>]
```
