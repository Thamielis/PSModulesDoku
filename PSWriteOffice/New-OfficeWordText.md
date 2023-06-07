New-OfficeWordText
------------------




### Synopsis

New-OfficeWordText [[-Document] <WordDocument>] [[-Paragraph] <WordParagraph>] [[-Text] <string[]>] [[-Bold] <Nullable[bool][]>] [[-Italic] <Nullable[bool][]>] [[-Underline] <Nullable[UnderlineValues][]>] [[-Color] <string[]>] [[-Alignment] <JustificationValues>] [-ReturnObject] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Alignment**

Valid Values:

* Left
* Start
* Center
* Right
* End
* Both
* MediumKashida
* Distribute
* NumTab
* HighKashida
* LowKashida
* ThaiDistribute






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[JustificationValues]`|false   |7       |false        |



#### **Bold**




|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[Nullable[bool][]]`|false   |3       |false        |



#### **Color**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|false   |6       |false        |



#### **Document**




|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[WordDocument]`|false   |0       |false        |



#### **Italic**




|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[Nullable[bool][]]`|false   |4       |false        |



#### **Paragraph**




|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[WordParagraph]`|false   |1       |false        |



#### **ReturnObject**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Text**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|false   |2       |false        |



#### **Underline**




|Type                           |Required|Position|PipelineInput|
|-------------------------------|--------|--------|-------------|
|`[Nullable[UnderlineValues][]]`|false   |5       |false        |





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
{@{name=New-OfficeWordText; CommonParameters=True; parameter=System.Object[]}}
```
