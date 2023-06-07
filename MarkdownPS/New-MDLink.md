New-MDLink
----------




### Synopsis
This commandlet output link in markdown syntax



---


### Description

This commandlet output link in markdown syntax like this [text](link "title")



---


### Related Links
* [New-MDImage
https://help.github.com/articles/basic-writing-and-formatting-syntax/](New-MDImage
https://help.github.com/articles/basic-writing-and-formatting-syntax/)





---


### Examples
#### EXAMPLE 1
```PowerShell
New-MDLink -Text "Example" -Link "http://example.com"
"example.png" | New-MDLink -Link "http://example.com"
```
[Example](http://example.com)
#### EXAMPLE 2
```PowerShell
New-MDLink -Text "Example" -Link "http://example.com" -Title "This is an example link"
"example.png" | New-MDLink -Link "http://example.com" -Title "This is an example link"
```
[Example](http://example.com "This is an example link")


---


### Parameters
#### **Text**

Text of the link






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[String]`|true    |1       |true (ByValue)|



#### **Link**

The link






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **Title**

The title of the link






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |





---


### Inputs
Any text



---


### Outputs
* The link construct in markdown






---


### Syntax
```PowerShell
New-MDLink [-Text] <String> -Link <String> [-Title <String>] [<CommonParameters>]
```
