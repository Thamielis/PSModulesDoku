ConvertFrom-HTMLToMarkdown
--------------------------




### Synopsis
Converts HTML to Markdown file



---


### Description

Converts HTML to Markdown file.
Supports all the established html tags like h1, h2, h3, h4, h5, h6, p, em, strong, i, b, blockquote, code, img, a, hr, li, ol, ul, table, tr, th, td, br
Can deal with nested lists.
Github Flavoured Markdown conversion supported for br, pre and table.



---


### Examples
#### EXAMPLE 1
```PowerShell
ConvertFrom-HTMLToMarkdown -Path  "$PSScriptRoot\Input\Example01.html" -UnknownTags Drop -GithubFlavored -DestinationPath $PSScriptRoot\Output\Example01.md
```



---


### Parameters
#### **Path**

Path to HTML file






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **Content**

Content as given from variable






|Type      |Required|Position|PipelineInput                 |
|----------|--------|--------|------------------------------|
|`[String]`|true    |named   |true (ByValue, ByPropertyName)|



#### **DestinationPath**

Path where to save Markdown file. If not given it will output to variable






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **UnknownTags**

PassThrough - Include the unknown tag completely into the result. That is, the tag along with the text will be left in output. This is the default
Drop - Drop the unknown tag and its content
Bypass - Ignore the unknown tag but try to convert its content
Raise - Raise an error to let you know



Valid Values:

* PassThrough
* Drop
* Bypass
* Raise






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[UnknownTagsOption]`|false   |named   |false        |



#### **ListBulletChar**

Allows to change the bullet character. Default value is -. Some systems expect the bullet character to be * rather than -, this config allows to change it.



Valid Values:

* -
* *






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **WhitelistUriSchemes**

Specify which schemes (without trailing colon) are to be allowed for <a> and <img> tags. Others will be bypassed (output text or nothing). By default allows everything.
If string.Empty provided and when href or src schema coudn't be determined - whitelists
Schema is determined by Uri class, with exception when url begins with / (file schema) and // (http schema)






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **DefaultCodeBlockLanguage**

Allows to define default language for code blocks






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **TableWithoutHeaderRowHandling**

Default - First row will be used as header row (default)
EmptyRow - An empty row will be added as the header row



Valid Values:

* Default
* EmptyRow






|Type                                   |Required|Position|PipelineInput|
|---------------------------------------|--------|--------|-------------|
|`[TableWithoutHeaderRowHandlingOption]`|false   |named   |false        |



#### **RemoveComments**

Remove comment tags with text. Default is false






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **SmartHrefHandling**

false - Outputs [{name}]({href}{title}) even if name and href is identical. This is the default option.
true - If name and href equals, outputs just the name. Note that if Uri is not well formed as per Uri.IsWellFormedUriString (i.e string is not correctly escaped like http://example.com/path/file name.docx) then markdown syntax will be used anyway.
If href contains http/https protocol, and name doesn't but otherwise are the same, output href only
If tel: or mailto: scheme, but afterwards identical with name, output name only.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **GithubFlavored**

Github style markdown for br, pre and table. Default is false






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **RulesBefore**

Replaces given rules with empty string






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Array]`|false   |named   |false        |



#### **RulesAfter**

Replaces given rules with empty string






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Array]`|false   |named   |false        |



#### **Format**

Tries to format markdown






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
ConvertFrom-HTMLToMarkdown -Path <String> [-DestinationPath <String>] [-UnknownTags {PassThrough | Drop | Bypass | Raise}] [-ListBulletChar <String>] [-WhitelistUriSchemes <String>] [-DefaultCodeBlockLanguage <String>] [-TableWithoutHeaderRowHandling {Default | EmptyRow}] [-RemoveComments] [-SmartHrefHandling] [-GithubFlavored] [-RulesBefore <Array>] [-RulesAfter <Array>] [-Format] [<CommonParameters>]
```
```PowerShell
ConvertFrom-HTMLToMarkdown -Content <String> [-DestinationPath <String>] [-UnknownTags {PassThrough | Drop | Bypass | Raise}] [-ListBulletChar <String>] [-WhitelistUriSchemes <String>] [-DefaultCodeBlockLanguage <String>] [-TableWithoutHeaderRowHandling {Default | EmptyRow}] [-RemoveComments] [-SmartHrefHandling] [-GithubFlavored] [-RulesBefore <Array>] [-RulesAfter <Array>] [-Format] [<CommonParameters>]
```
