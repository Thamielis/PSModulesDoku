Set-DalleImageAsWallpaper
-------------------------




### Synopsis
Sets a DALL-E image as the desktop background



---


### Description


---


### Examples
#### EXAMPLE 1
```PowerShell
Set-DalleImageAsBackground "A picture of a cat"
```

#### EXAMPLE 2
```PowerShell
Set-DalleImageAsBackground "A picture of a cat" -Size 512
```



---


### Parameters
#### **Description**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **Size**

Valid Values:

* 256
* 512
* 1024






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |2       |false        |





---


### Syntax
```PowerShell
Set-DalleImageAsWallpaper [-Description] <Object> [[-Size] <Object>] [<CommonParameters>]
```
