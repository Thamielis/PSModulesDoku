New-AdaptiveTextBlock
---------------------




### Synopsis
Displays text, allowing control over font sizes, weight, and color.



---


### Description

Displays text, allowing control over font sizes, weight, and color.



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



---


### Parameters
#### **Text**

Text to display. A subset of markdown is supported (https://aka.ms/ACTextFeatures)






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |1       |false        |



#### **Color**

Controls the color of TextBlock elements.



Valid Values:

* Accent
* Default
* Dark
* Light
* Good
* Warning
* Attention






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |



#### **FontType**

Type of font to use for rendering



Valid Values:

* Default
* Monospace






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |3       |false        |



#### **HorizontalAlignment**

Controls the horizontal text alignment.



Valid Values:

* Left
* Center
* Right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |4       |false        |



#### **Subtle**

Displays text slightly toned down to appear less prominent.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **MaximumLines**

Specifies the maximum number of lines to display.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |5       |false        |



#### **Size**

Controls size of text.



Valid Values:

* Small
* Default
* Medium
* Large
* ExtraLarge






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |6       |false        |FontSize|



#### **Weight**

Controls the weight of TextBlock elements.



Valid Values:

* Lighter
* Default
* Bolder






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |7       |false        |FontWeight|



#### **Highlight**

Controls the hightlight of text elements






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **Italic**

Controls italic of text elements






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **StrikeThrough**

Controls strikethrough of text elements






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **Wrap**

Allow text to wrap. Otherwise, text is clipped.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **Height**

Specifies the height of the element.



Valid Values:

* Stretch
* Automatic






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|false   |8       |false        |BlockElementHeight|



#### **Separator**

Draw a separating line at the top of the element.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



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
|`[String]`|false   |9       |false        |



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





---


### Notes
General notes



---


### Syntax
```PowerShell
New-AdaptiveTextBlock [[-Text] <String>] [[-Color] <String>] [[-FontType] <String>] [[-HorizontalAlignment] <String>] [-Subtle] [[-MaximumLines] <Int32>] [[-Size] <String>] [[-Weight] <String>] [-Highlight] [-Italic] [-StrikeThrough] [-Wrap] [[-Height] <String>] [-Separator] [[-Spacing] <String>] [[-Id] <String>] [-Hidden] [<CommonParameters>]
```
