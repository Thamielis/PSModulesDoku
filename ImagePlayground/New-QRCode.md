New-ImageQRCode
---------------




### Synopsis
Creates QR code



---


### Description

Creates QR code



---


### Examples
#### EXAMPLE 1
```PowerShell
New-ImageQRCode -Content 'https://evotec.xyz' -FilePath "$PSScriptRoot\Samples\QRCode.png" -Verbose
```



---


### Parameters
#### **Content**

Content to be encoded in QR code






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **FilePath**

File path to where the image with QR code should be saved.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |2       |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
New-ImageQRCode [-Content] <String> [-FilePath] <String> [<CommonParameters>]
```
