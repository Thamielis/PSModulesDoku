Get-DalleImage
--------------




### Synopsis
Get a DALL-E image from the OpenAI API



---


### Description

Given a description, the model will return an image



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-DalleImage -Description "A cat sitting on a table"
```



---


### Parameters
#### **Description**

The description to generate an image for






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **Size**

The size of the image to generate. Defaults to 256



Valid Values:

* 256
* 512
* 1024






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |2       |false        |



#### **Raw**

If set, the raw response will be returned. Otherwise, the image will be saved to a temporary file and the path to that file will be returned






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **NoProgress**

The option to hide write-progress if you want, you could also set $ProgressPreference to SilentlyContinue






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Syntax
```PowerShell
Get-DalleImage [-Description] <Object> [[-Size] <Object>] [-Raw] [-NoProgress] [<CommonParameters>]
```
