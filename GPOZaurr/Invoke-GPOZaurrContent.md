Invoke-GPOZaurrContent
----------------------




### Synopsis

Invoke-GPOZaurrContent [-Forest <string>] [-ExcludeDomains <string[]>] [-IncludeDomains <string[]>] [-ExtendedForestInformation <IDictionary>] [-Type <string[]>] [-Splitter <string>] [-FullObjects] [-OutputType <string[]>] [-OutputPath <string>] [-Open] [-Online] [-CategoriesOnly] [-SingleObject] [-SkipNormalize] [-SkipCleanup] [-Extended] [<CommonParameters>]

Invoke-GPOZaurrContent [-GPOPath <string>] [-Type <string[]>] [-Splitter <string>] [-FullObjects] [-OutputType <string[]>] [-OutputPath <string>] [-Open] [-Online] [-CategoriesOnly] [-SingleObject] [-SkipNormalize] [-SkipCleanup] [-Extended] [<CommonParameters>]




---


### Description


---


### Parameters
#### **CategoriesOnly**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **ExcludeDomains**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|false   |Named   |false        |



#### **Extended**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **ExtendedForestInformation**




|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[IDictionary]`|false   |Named   |false        |



#### **Forest**




|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[string]`|false   |Named   |false        |ForestName|



#### **FullObjects**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **GPOPath**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |Named   |false        |



#### **IncludeDomains**




|Type        |Required|Position|PipelineInput|Aliases           |
|------------|--------|--------|-------------|------------------|
|`[string[]]`|false   |Named   |false        |Domain<br/>Domains|



#### **Online**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Open**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **OutputPath**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |Named   |false        |



#### **OutputType**

Valid Values:

* HTML
* Object






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|false   |Named   |false        |



#### **SingleObject**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **SkipCleanup**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **SkipNormalize**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Splitter**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |Named   |false        |



#### **Type**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|false   |Named   |false        |





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
{@{name=Invoke-GPOZaurrContent; CommonParameters=True; parameter=System.Object[]}, @{name=Invoke-GPOZaurrContent; CommonParameters=True; parameter=System.Object[]}}
```
