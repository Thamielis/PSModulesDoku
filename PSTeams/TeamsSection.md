New-TeamsSection
----------------




### Synopsis

New-TeamsSection [[-SectionInput] <scriptblock>] [[-Title] <string>] [[-ActivityTitle] <string>] [[-ActivitySubtitle] <string>] [[-ActivityImageLink] <string>] [[-ActivityImage] <string>] [[-ActivityImagePath] <FileInfo>] [[-ActivityText] <string>] [[-Text] <string>] [[-ActivityDetails] <IDictionary[]>] [[-Buttons] <IDictionary[]>] [-StartGroup] [<CommonParameters>]




---


### Description


---


### Parameters
#### **ActivityDetails**




|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IDictionary[]]`|false   |9       |false        |



#### **ActivityImage**

Valid Values:

* Alert
* Cancel
* Disable
* Download
* Minus
* Check
* Add
* None






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |5       |false        |



#### **ActivityImageLink**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |4       |false        |



#### **ActivityImagePath**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[FileInfo]`|false   |6       |false        |



#### **ActivitySubtitle**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |3       |false        |



#### **ActivityText**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |7       |false        |



#### **ActivityTitle**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |2       |false        |



#### **Buttons**




|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IDictionary[]]`|false   |10      |false        |



#### **SectionInput**




|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[scriptblock]`|false   |0       |false        |



#### **StartGroup**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Text**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |8       |false        |



#### **Title**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |1       |false        |





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
{@{name=New-TeamsSection; CommonParameters=True; parameter=System.Object[]}}
```
