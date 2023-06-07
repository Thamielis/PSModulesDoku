Merge-Image
-----------




### Synopsis
Merges two images into a single image



---


### Description

Merges two images into a single image



---


### Examples
#### EXAMPLE 1
```PowerShell
Merge-Image -FilePath "C:\Users\przemyslaw.klys\Downloads\IMG_4644.jpeg" -FilePathToMerge "C:\Users\przemyslaw.klys\Downloads\IMG_4644.jpeg" -FilePathOutput "C:\Users\przemyslaw.klys\Downloads\IMG_4644.jpeg" -ResizeToFit -Placement Bottom
```



---


### Parameters
#### **FilePath**

File path to image to be processed for merging of images. This image will be the base image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |1       |false        |



#### **FilePathToMerge**

File path to image to be merged into the base image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |



#### **FilePathOutput**

File path to output image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |3       |false        |



#### **ResizeToFit**

Resize the image to fit the base image. If not specified, the image will be added as is.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **Placement**

Placement of the image to be merged. Default is bottom. Possible values: Top, Bottom, Left, Right



Valid Values:

* Bottom
* Right
* Top
* Left






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[ImagePlacement]`|false   |4       |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Merge-Image [[-FilePath] <String>] [[-FilePathToMerge] <String>] [[-FilePathOutput] <String>] [-ResizeToFit] [[-Placement] {Bottom | Right | Top | Left}] [<CommonParameters>]
```
