Resize-Image
------------




### Synopsis
Resizes the image to given width and height or percentage.



---


### Description

Resizes the image to given width and height or percentage.
By default it will respect aspect ratio. If you want to ignore it use -DontRespectAspectRatio switch.
This means you can only provide Width and the height will be automatically calculated or vice versa.
You can also use percentage to resize the image maintaining the aspect ratio.



---


### Examples
#### EXAMPLE 1
```PowerShell
Resize-Image -FilePath $PSScriptRoot\Samples\LogoEvotec.png -OutputPath $PSScriptRoot\Output\LogoEvotecResize.png -Width 100 -Height 100
```

#### EXAMPLE 2
```PowerShell
Resize-Image -FilePath $PSScriptRoot\Samples\LogoEvotec.png -OutputPath $PSScriptRoot\Output\LogoEvotecResizeMaintainAspectRatio.png -Width 300
```

#### EXAMPLE 3
```PowerShell
Resize-Image -FilePath $PSScriptRoot\Samples\LogoEvotec.png -OutputPath $PSScriptRoot\Output\LogoEvotecResizePercent.png -Percentage 200
```



---


### Parameters
#### **FilePath**

File path to the image you want to resize






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **OutputPath**

File path to the output image that will be created






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **Width**

New width of the image






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |false        |



#### **Height**

New height of the image






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |false        |



#### **Percentage**

Percentage of the image to resize






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |false        |



#### **DontRespectAspectRatio**

If you want to ignore aspect ratio use this switch. It only affects Width and Height parameters that are used separately.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Resize-Image [-FilePath <String>] [-OutputPath <String>] [-Width <Int32>] [-Height <Int32>] [-DontRespectAspectRatio] [<CommonParameters>]
```
```PowerShell
Resize-Image [-FilePath <String>] [-OutputPath <String>] [-Percentage <Int32>] [<CommonParameters>]
```
