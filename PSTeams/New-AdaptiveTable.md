New-AdaptiveTable
-----------------




### Synopsis
Simplifies process of creating an adaptive table by working with PowerShell objects



---


### Description

Simplifies process of creating an adaptive table by working with PowerShell objects



---


### Examples
#### EXAMPLE 1
```PowerShell
$Card = New-AdaptiveCard {
    New-AdaptiveTextBlock -Size 'Medium' -Weight Bolder -Text 'Table usage with PSCustomObject' -Separator -Wrap
```
New-AdaptiveTable -DataTable $Objects

    New-AdaptiveTextBlock -Size 'Medium' -Weight Bolder -Text 'Table usage with OrderedDictionary' -Separator -Wrap

    New-AdaptiveTable -DataTable $ObjectsHashes
} -Uri $Env:TEAMSPESTERID


---


### Parameters
#### **DataTable**

Provide a data table to be converted to an adaptive table






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Array]`|false   |1       |false        |



#### **HeaderColor**

Provide a color to be used for the header row of the table. By default, the header row is set to 'Accent'



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



#### **HeaderWeight**

Provide a weight to be used for the header row of the table. By default, the header row is set to 'Bolder'



Valid Values:

* Lighter
* Default
* Bolder






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|false   |3       |false        |HeaderFontWeight|



#### **HeaderSize**

Controls size of text.



Valid Values:

* Small
* Default
* Medium
* Large
* ExtraLarge






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |4       |false        |HeaderFontSize|



#### **HeaderHighlight**

Controls the hightlight of text elements






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **HeaderItalic**

Controls italic of text elements






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **HeaderStrikeThrough**

Controls strikethrough of text elements






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **HeaderFontType**

Type of font to use for rendering



Valid Values:

* Default
* Monospace






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |5       |false        |



#### **HeaderSpacing**

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
|`[String]`|false   |6       |false        |



#### **HeaderHorizontalAlignment**

Controls the horizontal text alignment.



Valid Values:

* Left
* Center
* Right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |7       |false        |



#### **HeaderHeight**

Specifies the height of the element.



Valid Values:

* Stretch
* Automatic






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|false   |8       |false        |HeaderBlockElementHeight|



#### **HeaderSubtle**

Displays text slightly toned down to appear less prominent.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **HeaderMaximumLines**

Specifies the maximum number of lines to display.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |9       |false        |



#### **Weight**

Controls the weight of TextBlock elements.



Valid Values:

* Lighter
* Default
* Bolder






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |10      |false        |FontWeight|



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
|`[String]`|false   |11      |false        |FontSize|



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
|`[String]`|false   |12      |false        |



#### **Highlight**

Controls the hightlight of text elements






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |13      |false        |



#### **Italic**

Controls italic of text elements






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |14      |false        |



#### **StrikeThrough**

Controls strikethrough of text elements






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |15      |false        |



#### **FontType**

Type of font to use for rendering



Valid Values:

* Default
* Monospace






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |16      |false        |



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
|`[String]`|false   |17      |false        |



#### **HorizontalAlignment**

Controls the horizontal text alignment.



Valid Values:

* Left
* Center
* Right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |18      |false        |



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
|`[String]`|false   |19      |false        |BlockElementHeight|



#### **Subtle**

Displays text slightly toned down to appear less prominent.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **MaximumLines**

Specifies the maximum number of lines to display.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |20      |false        |



#### **DictionaryAsCustomObject**

Forces display of Dictionary the same way as a custom object. By default, the Dictionary is displayed the way you see with Format-Table






|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[Switch]`|false   |named   |false        |HashTableAsCustomObject|





---


### Notes
General notes



---


### Syntax
```PowerShell
New-AdaptiveTable [[-DataTable] <Array>] [[-HeaderColor] <String>] [[-HeaderWeight] <String>] [[-HeaderSize] <String>] [-HeaderHighlight] [-HeaderItalic] [-HeaderStrikeThrough] [[-HeaderFontType] <String>] [[-HeaderSpacing] <String>] [[-HeaderHorizontalAlignment] <String>] [[-HeaderHeight] <String>] [-HeaderSubtle] [[-HeaderMaximumLines] <Int32>] [[-Weight] <String>] [[-Size] <String>] [[-Color] <String>] [[-Highlight] <Boolean>] [[-Italic] <Boolean>] [[-StrikeThrough] <Boolean>] [[-FontType] <String[]>] [[-Spacing] <String>] [[-HorizontalAlignment] <String>] [-Wrap] [[-Height] <String>] [-Subtle] [[-MaximumLines] <Int32>] [-DictionaryAsCustomObject] [<CommonParameters>]
```
