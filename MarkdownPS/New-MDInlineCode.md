New-MDInlineCode
----------------




### Synopsis
This commandlet output inline code in markdown syntax



---


### Description

This commandlet output inline code in markdown syntax by wrapping the text in `



---


### Related Links
* [New-MDQuote
New-MDCharacterStyle
https://help.github.com/articles/basic-writing-and-formatting-syntax/](New-MDQuote
New-MDCharacterStyle
https://help.github.com/articles/basic-writing-and-formatting-syntax/)





---


### Examples
#### EXAMPLE 1
```PowerShell
New-MDInlineCode -Text "Inline Code"
"Inline Code" | New-MDInlineCode
```
`Inline Code`


---


### Parameters
#### **Text**

Any text






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[String]`|true    |1       |true (ByValue)|





---


### Inputs
Any text



---


### Outputs
* The input wrapped in `






---


### Syntax
```PowerShell
New-MDInlineCode [-Text] <String> [<CommonParameters>]
```
