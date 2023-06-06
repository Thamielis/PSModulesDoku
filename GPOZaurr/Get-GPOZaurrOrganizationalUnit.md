Get-GPOZaurrOrganizationalUnit
------------------------------




### Synopsis

Get-GPOZaurrOrganizationalUnit [[-Forest] <string>] [[-ExcludeDomains] <string[]>] [[-IncludeDomains] <string[]>] [[-ExtendedForestInformation] <IDictionary>] [[-Option] <string[]>] [[-ExcludeOrganizationalUnit] <string[]>] [<CommonParameters>]




---


### Description


---


### Parameters
#### **ExcludeDomains**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|false   |1       |false        |



#### **ExcludeOrganizationalUnit**




|Type        |Required|Position|PipelineInput|Aliases                 |
|------------|--------|--------|-------------|------------------------|
|`[string[]]`|false   |5       |false        |ExcludeOU<br/>Exclusions|



#### **ExtendedForestInformation**




|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[IDictionary]`|false   |3       |false        |



#### **Forest**




|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[string]`|false   |0       |false        |ForestName|



#### **IncludeDomains**




|Type        |Required|Position|PipelineInput|Aliases           |
|------------|--------|--------|-------------|------------------|
|`[string[]]`|false   |2       |false        |Domain<br/>Domains|



#### **Option**

Valid Values:

* OK
* Unlink
* Delete






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|false   |4       |false        |





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
{@{name=Get-GPOZaurrOrganizationalUnit; CommonParameters=True; parameter=System.Object[]}}
```
