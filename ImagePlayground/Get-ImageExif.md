Get-ImageExif
-------------




### Synopsis
Gets EXIF data from image



---


### Description

Gets EXIF data from image.



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-ImageExif -FilePath "C:\Users\przemyslaw.klys\Downloads\IMG_4644.jpeg"
```



---


### Parameters
#### **FilePath**

File path to image to be processed for Exif Tag reading






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **Translate**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Get-ImageExif [-FilePath] <String> [-Translate] [<CommonParameters>]
```
