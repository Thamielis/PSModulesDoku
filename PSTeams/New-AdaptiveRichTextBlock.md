New-AdaptiveRichTextBlock
-------------------------




### Synopsis
Defines an array of inlines, allowing for inline text formatting.



---


### Description

Defines an array of inlines, allowing for inline text formatting.



---


### Examples
#### EXAMPLE 1
```PowerShell
New-AdaptiveRichTextBlock -Text 'This is the first inline.', 'We support colors,', 'both regular and subtle. ', 'Monospace too!' -Color Attention, Default, Warning -StrikeThrough $false, $true, $false -Size ExtraLarge, Default, Medium -Italic $false, $false, $true -Subtle $false, $true, $true
```



---


### Parameters
#### **Text**

Text to display.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |1       |false        |



#### **Color**

Controls the color of text elements.



Valid Values:

* Accent
* Default
* Dark
* Light
* Good
* Warning
* Attention






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |2       |false        |



#### **Subtle**

Displays text slightly toned down to appear less prominent.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Boolean[]]`|false   |3       |false        |



#### **Size**

Controls size of text.



Valid Values:

* Small
* Default
* Medium
* Large
* ExtraLarge






|Type        |Required|Position|PipelineInput|Aliases |
|------------|--------|--------|-------------|--------|
|`[String[]]`|false   |4       |false        |FontSize|



#### **Weight**

Controls the weight of text elements.



Valid Values:

* Lighter
* Default
* Bolder






|Type        |Required|Position|PipelineInput|Aliases   |
|------------|--------|--------|-------------|----------|
|`[String[]]`|false   |5       |false        |FontWeight|



#### **Highlight**

Controls the hightlight of text elements






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Boolean[]]`|false   |6       |false        |



#### **Italic**

Controls italic of text elements






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Boolean[]]`|false   |7       |false        |



#### **StrikeThrough**

Controls strikethrough of text elements






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Boolean[]]`|false   |8       |false        |



#### **FontType**

Type of font to use for rendering



Valid Values:

* Default
* Monospace






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |9       |false        |



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
|`[String]`|false   |10      |false        |



#### **Separator**

Draw a separating line at the top of the element.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **HorizontalAlignment**

Controls the horizontal text alignment.



Valid Values:

* Left
* Center
* Right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |11      |false        |



#### **Height**

Specifies the height of the element.



Valid Values:

* Stretch
* Automatic






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |12      |false        |



#### **Id**

A unique identifier associated with the item.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |13      |false        |



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
New-AdaptiveRichTextBlock [[-Text] <String[]>] [[-Color] <String[]>] [[-Subtle] <Boolean[]>] [[-Size] <String[]>] [[-Weight] <String[]>] [[-Highlight] <Boolean[]>] [[-Italic] <Boolean[]>] [[-StrikeThrough] <Boolean[]>] [[-FontType] <String[]>] [[-Spacing] <String>] [-Separator] [[-HorizontalAlignment] <String>] [[-Height] <String>] [[-Id] <String>] [-Hidden] [<CommonParameters>]
```
