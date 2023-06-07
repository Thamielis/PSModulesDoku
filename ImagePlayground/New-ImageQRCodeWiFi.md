New-ImageQRCodeWiFi
-------------------




### Synopsis
Creates QR code for WiFi connection



---


### Description

Creates QR code for WiFi connection



---


### Examples
#### EXAMPLE 1
```PowerShell
New-ImageQRCodeWiFi -SSID 'Evotec' -Password 'Evotec' -FilePath "$PSScriptRoot\Samples\QRCodeWiFi.png"
```



---


### Parameters
#### **SSID**

SSID of the WiFi network






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **Password**

Password of the WiFi network






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |2       |false        |



#### **FilePath**

File path to where the image with QR code should be saved.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |3       |false        |



#### **Show**

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
New-ImageQRCodeWiFi [-SSID] <String> [-Password] <String> [-FilePath] <String> [-Show] [<CommonParameters>]
```
