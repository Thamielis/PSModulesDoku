New-AdaptiveCard
----------------




### Synopsis
An Adaptive Card, containing a free-form body of card elements, and an optional set of actions.



---


### Description

An Adaptive Card, containing a free-form body of card elements, and an optional set of actions.



---


### Examples
#### EXAMPLE 1
```PowerShell
New-AdaptiveCard -Uri $Env:TEAMSPESTERID -VerticalContentAlignment center {
    New-AdaptiveTextBlock -Size ExtraLarge -Weight Bolder -Text 'Test' -Color Attention -HorizontalAlignment Center
    New-AdaptiveColumnSet {
        New-AdaptiveColumn {
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Dark
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Light
        }
        New-AdaptiveColumn {
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Warning
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Good
        }
    }
} -SelectAction Action.OpenUrl -SelectActionUrl 'https://evotec.xyz' -Verbose
```

#### EXAMPLE 2
```PowerShell
New-AdaptiveCard -Uri $Env:TEAMSPESTERID -VerticalContentAlignment center {
    New-AdaptiveTextBlock -Size ExtraLarge -Weight Bolder -Text 'Test' -Color Attention -HorizontalAlignment Center
    New-AdaptiveColumnSet {
        New-AdaptiveColumn {
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Dark
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Light
        }
        New-AdaptiveColumn {
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Warning
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Good
        }
        New-AdaptiveColumn {
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1 <at>Name</at>' -Color Warning
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1 <at>Zenon Jaskuła</at>' -Color Warning
        }
    }
    New-AdaptiveMention -Text 'Zenon Jaskuła' -UserPrincipalName 'przemyslaw.klys@evotec.test'
    New-AdaptiveMention -Text 'Name' -UserPrincipalName 'przemyslaw.klys@evotec.test'
} -Verbose -FullWidth
```



---


### Parameters
#### **Body**

The card elements to show in the primary card region.






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ScriptBlock]`|false   |1       |false        |



#### **Action**

The Actions to show in the card's action bar.






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ScriptBlock]`|false   |2       |false        |



#### **Uri**

WebHook Uri to send Adaptive Card to. When provided sends Adaptive Card. When not provided JSON is returned.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |3       |false        |



#### **FallBackText**

Text shown when the client doesn't support the version specified (may contain markdown).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |4       |false        |



#### **MinimumHeight**

Specifies the minimum height of the card.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |5       |false        |



#### **Speak**

Specifies what should be spoken for this entire card. This is simple text or SSML fragment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |6       |false        |



#### **Language**

The 2-letter ISO-639-1 language used in the card. Used to localize any date/time functions.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |7       |false        |



#### **VerticalContentAlignment**

Defines how the content should be aligned vertically within the container. Only relevant for fixed-height cards, or cards with a minHeight specified.



Valid Values:

* top
* center
* bottom






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |8       |false        |



#### **BackgroundUrl**

Specifies a background image. Acceptable formats are PNG, JPEG, and GIF






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |9       |false        |



#### **BackgroundFillMode**

Controls how background is displayed

"cover": The background image covers the entire width of the container. Its aspect ratio is preserved. Content may be clipped if the aspect ratio of the image doesn't match the aspect ratio of the container. verticalAlignment is respected (horizontalAlignment is meaningless since it's stretched width). This is the default mode and is the equivalent to the current model.
"repeatHorizontally": The background image isn't stretched. It is repeated in the x axis as many times as necessary to cover the container's width. verticalAlignment is honored (default is top), horizontalAlignment is ignored.
"repeatVertically": The background image isn't stretched. It is repeated in the y axis as many times as necessary to cover the container's height. verticalAlignment is ignored, horizontalAlignment is honored (default is left).
"repeat": The background image isn't stretched. It is repeated first in the x axis then in the y axis as many times as necessary to cover the entire container. Both horizontalAlignment and verticalAlignment are honored (defaults are left and top).



Valid Values:

* Cover
* RepeatHorizontally
* RepeatVertically
* Repeat






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |10      |false        |



#### **BackgroundHorizontalAlignment**

Controls how background is aligned horizontally



Valid Values:

* left
* center
* right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |11      |false        |



#### **BackgroundVerticalAlignment**

Controls how background is aligned vertically



Valid Values:

* top
* center
* bottom






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |12      |false        |



#### **SelectAction**

An Action that will be invoked when the card is tapped or selected.



Valid Values:

* Action.Submit
* Action.OpenUrl
* Action.ToggleVisibility






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |13      |false        |



#### **SelectActionId**

Provide ID for Select Action






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |14      |false        |



#### **SelectActionUrl**

Provide URL to open when using SelectAction with Action.OpenUrl






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |15      |false        |



#### **SelectActionTitle**

Provide Title for Select Action






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |16      |false        |



#### **FullWidth**

Provide ability to make card full width. By default it set to small.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **AllowImageExpand**

Defines that image may expand






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **ReturnJson**

Defines that JSON should be returned even when Uri is provided. Useful for debugging






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
New-AdaptiveCard [[-Body] <ScriptBlock>] [[-Action] <ScriptBlock>] [[-Uri] <String>] [[-FallBackText] <String>] [[-MinimumHeight] <Int32>] [[-Speak] <String>] [[-Language] <String>] [[-VerticalContentAlignment] <String>] [[-BackgroundUrl] <String>] [[-BackgroundFillMode] <String>] [[-BackgroundHorizontalAlignment] <String>] [[-BackgroundVerticalAlignment] <String>] [[-SelectAction] <String>] [[-SelectActionId] <String>] [[-SelectActionUrl] <String>] [[-SelectActionTitle] <String>] [-FullWidth] [-AllowImageExpand] [-ReturnJson] [<CommonParameters>]
```
