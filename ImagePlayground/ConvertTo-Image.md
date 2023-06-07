ConvertTo-Image
---------------




### Synopsis
Converts the image to the specified format.



---


### Description

Converts the image to the specified format. The output path must include the file extension.



---


### Examples
#### EXAMPLE 1
```PowerShell
ConvertTo-Image -FilePath $PSScriptRoot\Samples\LogoEvotec.png -OutputPath $PSScriptRoot\Output\LogoEvotec.jpg
```



---


### Parameters
#### **FilePath**

File path to the image you want to convert.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **OutputPath**

File path to the output image that will be created.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |2       |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
ConvertTo-Image [-FilePath] <String> [-OutputPath] <String> [<CommonParameters>]
```
