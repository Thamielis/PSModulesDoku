New-MDImage
-----------




### Synopsis
This commandlet output image in markdown syntax



---


### Description

This commandlet output image in markdown syntax like this ![alt text](link "title")



---


### Related Links
* [New-MDLink
https://help.github.com/articles/basic-writing-and-formatting-syntax/
https://img.shields.io/badge/<SUBJECT>-<STATUS>-<COLOR>.svg
http://shields.io/](New-MDLink
https://help.github.com/articles/basic-writing-and-formatting-syntax/
https://img.shields.io/badge/<SUBJECT>-<STATUS>-<COLOR>.svg
http://shields.io/)





---


### Examples
#### EXAMPLE 1
```PowerShell
New-MDImage -Link "example.png"
"example.png" | New-MDImage
```
![](example.png)
#### EXAMPLE 2
```PowerShell
New-MDImage -Link "example.png" -Title "Example"
"example.png" | New-MDImage -Title "Example"
```
![](example.png "Example")
#### EXAMPLE 3
```PowerShell
New-MDImage -Link "example.png" -Title "Example" -AltText "Failed to load"
"example.png" | New-MDImage -Title "Example" -AltText "Failed to load"
```
![Failed to load](example.png "Example")
#### EXAMPLE 4
```PowerShell
New-MDImage -Subject "SUBJECT" -Status "STATUS" -Color "green"
```
![](https://img.shields.io/badge/SUBJECT-STATUS-green.svg)


---


### Parameters
#### **Source**

Text that represents the image source






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[String]`|false   |1       |true (ByValue)|



#### **Title**

The title of the image






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **AltText**

The alternative text of the image






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Subject**

The <SUBJECT> in https://img.shields.io/badge/<SUBJECT>-<STATUS>-<COLOR>.svg






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Status**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Color**

The <Color> in https://img.shields.io/badge/<SUBJECT>-<STATUS>-<COLOR>.svg
One of the brightgreen, green, yellowgreen, yellow, orange, red, lightgrey, blue



Valid Values:

* brightgreen
* green
* yellowgreen
* yellow
* orange
* red
* lightgrey
* blue






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Style**

The <STYLE> in https://img.shields.io/badge/<SUBJECT>-<STATUS>-<COLOR>.svg



Valid Values:

* plastic
* flat
* flat-square
* social






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Link**

Add a link to the image






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |





---


### Inputs
Any text representing link or parameters to drive shields.io badges



---


### Outputs
* The image construct in markdown






---


### Syntax
```PowerShell
New-MDImage [[-Source] <String>] [-Title <String>] [-AltText <String>] [-Link <String>] [<CommonParameters>]
```
```PowerShell
New-MDImage [-Title <String>] [-AltText <String>] [-Subject <String>] [-Status <String>] [-Color <String>] [-Style <String>] [-Link <String>] [<CommonParameters>]
```
