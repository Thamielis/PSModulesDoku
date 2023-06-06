Register-PDFFont
----------------




### Synopsis

Register-PDFFont [-FontName] <string> [-FontPath] <string> [[-Encoding] <string>] [[-EmbeddingStrategy] <PdfFontFactory+EmbeddingStrategy>] [-Cached] [-Default] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Cached**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Default**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **EmbeddingStrategy**

Valid Values:

* FORCE_EMBEDDED
* FORCE_NOT_EMBEDDED
* PREFER_EMBEDDED
* PREFER_NOT_EMBEDDED






|Type                                |Required|Position|PipelineInput|
|------------------------------------|--------|--------|-------------|
|`[PdfFontFactory+EmbeddingStrategy]`|false   |3       |false        |



#### **Encoding**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |2       |false        |



#### **FontName**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |0       |false        |



#### **FontPath**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |1       |false        |





---


### Inputs
None




---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Syntax
```PowerShell
syntaxItem
```
```PowerShell
----------
```
```PowerShell
{@{name=Register-PDFFont; CommonParameters=True; parameter=System.Object[]}}
```
