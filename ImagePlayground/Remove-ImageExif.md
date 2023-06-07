Remove-ImageExif
----------------




### Synopsis
Removes EXIF data from image



---


### Description

Removes EXIF data from image.



---


### Examples
#### EXAMPLE 1
```PowerShell
Remove-ImageExif -FilePath "C:\Users\przemyslaw.klys\Downloads\IMG_4644.jpeg" -ExifTag [SixLabors.ImageSharp.Metadata.Profiles.Exif.ExifTag]::ExposureTime
```

#### EXAMPLE 2
```PowerShell
Remove-ImageExif -FilePath "C:\Users\przemyslaw.klys\Downloads\IMG_4644.jpeg" -All
```



---


### Parameters
#### **FilePath**

File path to image to be processed for Exif Tag removal






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **FilePathOutput**

File path to where the image with removed Exif Tag should be saved. If not specified, the original image will be overwritten.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **ExifTag**

Exif Tag to be removed from image






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[ExifTag[]]`|true    |named   |false        |



#### **All**

Removes all Exif Tags from image






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Remove-ImageExif -FilePath <String> -FilePathOutput <String> -ExifTag <ExifTag[]> [<CommonParameters>]
```
```PowerShell
Remove-ImageExif -FilePath <String> -FilePathOutput <String> -All [<CommonParameters>]
```
