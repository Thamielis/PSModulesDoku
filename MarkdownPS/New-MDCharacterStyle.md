New-MDCharacterStyle
--------------------




### Synopsis
This commandlet output bold, italic or strikethrough in markdown syntax



---


### Description

This commandlet output bold, italic or strikethrough in markdown syntax by wrapping the text in **, * or ~~ respectively.



---


### Related Links
* [New-MDInlineCode](New-MDInlineCode)





---


### Examples
#### EXAMPLE 1
```PowerShell
New-MDCharacterStyle -Text "Bold" -Style "Bold"
"Bold" | New-MDCharacterStyle -Style "Bold"
```
**Bold**
#### EXAMPLE 2
```PowerShell
New-MDCharacterStyle -Text "Italic" -Style "Italic"
"Italic" | New-MDCharacterStyle -Style "Italic"
```
*Italic*
#### EXAMPLE 3
```PowerShell
New-MDCharacterStyle -Text "StrikeThrough" -Style "StrikeThrough"
"StrikeThrough" | New-MDCharacterStyle -Style "StrikeThrough"
```
~~StrikeThrough~~


---


### Parameters
#### **Text**

Any text






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[String]`|true    |1       |true (ByValue)|



#### **Style**

One of the Bold, Italic or StrikeThrough



Valid Values:

* Bold
* Italic
* StrikeThrough






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |





---


### Inputs
Any text



---


### Outputs
* The input wrapped in **, * or ~~ respectively for bold, italic or strikethrough






---


### Syntax
```PowerShell
New-MDCharacterStyle [-Text] <String> -Style <String> [<CommonParameters>]
```
