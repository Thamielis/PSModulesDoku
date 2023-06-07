Set-ImageExif
-------------




### Synopsis
Sets EXIF tag to specific value



---


### Description

Sets EXIF tag to specific value



---


### Examples
#### EXAMPLE 1
```PowerShell
$setImageExifSplat = @{
    FilePath       = "C:\Users\przemyslaw.klys\Downloads\IMG_4644.jpeg"
    ExifTag        = ([SixLabors.ImageSharp.Metadata.Profiles.Exif.ExifTag]::DateTimeOriginal)
    Value          = ([DateTime]::Now).ToString("yyyy:MM:dd HH:mm:ss")
    FilePathOutput = "$PSScriptRoot\Output\IMG_4644.jpeg"
}
```
Set-ImageExif @setImageExifSplat


---


### Parameters
#### **FilePath**

File path to image to be processed for Exif Tag manipulation. If FilePathOutput is not specified, the image will be overwritten.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **FilePathOutput**

File path to output image. If not specified, the image will be overwritten.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |



#### **ExifTag**

Exif Tag to be set






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[ExifTag]`|true    |3       |false        |



#### **Value**

Value to be set






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |4       |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Set-ImageExif [-FilePath] <String> [[-FilePathOutput] <String>] [-ExifTag] <ExifTag> [-Value] <Object> [<CommonParameters>]
```
