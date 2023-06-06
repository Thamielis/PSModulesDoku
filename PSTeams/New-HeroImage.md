New-AdaptiveImage
-----------------




### Synopsis
Displays an image. Acceptable formats are PNG, JPEG, and GIF



---


### Description

Displays an image. Acceptable formats are PNG, JPEG, and GIF



---


### Examples
#### EXAMPLE 1
```PowerShell
New-AdaptiveImage -BackgroundColor AlbescentWhite -Url 'https://devblogs.microsoft.com/powershell/wp-content/uploads/sites/30/2018/09/Powershell_256.png'
```

#### EXAMPLE 2
```PowerShell
New-AdaptiveImage -Url "https://pbs.twimg.com/profile_images/3647943215/d7f12830b3c17a5a9e4afcc370e3a37e_400x400.jpeg" -Size Small -Style person
```

#### EXAMPLE 3
```PowerShell
New-AdaptiveImage -Url "https://pbs.twimg.com/profile_images/3647943215/d7f12830b3c17a5a9e4afcc370e3a37e_400x400.jpeg" -Size Small -Style person -SelectAction Action.OpenUrl -SelectActionUrl 'https://evotec.xyz'
```

#### EXAMPLE 4
```PowerShell
New-HeroImage -Url 'https://upload.wikimedia.org/wikipedia/commons/thumb/4/49/Seattle_monorail01_2008-02-25.jpg/1024px-Seattle_monorail01_2008-02-25.jpg'
```

#### EXAMPLE 5
```PowerShell
New-ThumbnailImage -Url 'https://upload.wikimedia.org/wikipedia/en/a/a6/Bender_Rodriguez.png' -AltText "Bender Rodríguez"
```



---


### Parameters
#### **Url**

The URL to the image.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |1       |false        |Link   |



#### **Style**

Controls how this Image is displayed.



Valid Values:

* person
* default






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |



#### **AlternateText**

Alternate text describing the image.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |3       |false        |Alt<br/>AltText|



#### **Size**

Controls the approximate size of the image. The physical dimensions will vary per host.



Valid Values:

* Auto
* Stretch
* Small
* Medium
* Large






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |4       |false        |



#### **Spacing**

Controls the amount of spacing between this element and the preceding element.



Valid Values:

* None
* Small
* Default
* Medium
* Large
* ExtraLarge
* Padding






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |5       |false        |



#### **Separator**

Draw a separating line at the top of the element.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **HorizontalAlignment**

Controls how this element is horizontally positioned within its parent.



Valid Values:

* Left
* Center
* Right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |6       |false        |



#### **Height**

The desired height of the image.



Valid Values:

* Stretch
* Automatic






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |7       |false        |



#### **HeightInPixels**

The desired height of the image. Will be specified in pixel value. The image will distort to fit that exact height. This overrides the size property.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |8       |false        |



#### **WidthInPixels**

The desired on-screen width of the image. This overrides the size property.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |9       |false        |



#### **Id**

A unique identifier associated with the item.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |10      |false        |



#### **Hidden**

If used this item will be removed from the visual tree.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **BackgroundColor**

Applies a background to a transparent image. This property will respect the image style.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |11      |false        |



#### **SelectAction**

An Action that will be invoked when the card is tapped or selected.



Valid Values:

* Action.Submit
* Action.OpenUrl
* Action.ToggleVisibility






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |12      |false        |



#### **SelectActionId**

Provide ID for Select Action






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |13      |false        |



#### **SelectActionUrl**

Provide URL to open when using SelectAction with Action.OpenUrl






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |14      |false        |



#### **SelectActionTitle**

Provide Title for Select Action






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |15      |false        |



#### **SelectActionTargetElement**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |16      |false        |





---


### Notes
Adaptive Image supports most if not all of those options. However HeroImage and ThumbnailImage most likely support only some if not just what is shown in Examples.
I didn't want to create additional functions just for the sake of having more of them, as I expect most people using Adaptive Cards, and occasionally other types.



---


### Syntax
```PowerShell
New-AdaptiveImage [[-Url] <String>] [[-Style] <String>] [[-AlternateText] <String>] [[-Size] <String>] [[-Spacing] <String>] [-Separator] [[-HorizontalAlignment] <String>] [[-Height] <String>] [[-HeightInPixels] <Int32>] [[-WidthInPixels] <Int32>] [[-Id] <String>] [-Hidden] [[-BackgroundColor] <String>] [[-SelectAction] <String>] [[-SelectActionId] <String>] [[-SelectActionUrl] <String>] [[-SelectActionTitle] <String>] [[-SelectActionTargetElement] <String[]>] [<CommonParameters>]
```
