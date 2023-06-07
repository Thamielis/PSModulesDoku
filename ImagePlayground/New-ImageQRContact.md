New-ImageQRContact
------------------




### Synopsis

New-ImageQRContact [-FilePath] <string> [[-outputType] <PayloadGenerator+ContactData+ContactOutputType>] [[-Firstname] <string>] [[-Lastname] <string>] [[-Nickname] <string>] [[-Phone] <string>] [[-MobilePhone] <string>] [[-WorkPhone] <string>] [[-Email] <string>] [[-Birthday] <datetime>] [[-Website] <string>] [[-Street] <string>] [[-HouseNumber] <string>] [[-City] <string>] [[-ZipCode] <string>] [[-Country] <string>] [[-Note] <string>] [[-StateRegion] <string>] [[-AddressOrder] <string>] [[-Org] <string>] [[-OrgTitle] <string>] [-Show] [<CommonParameters>]




---


### Description


---


### Parameters
#### **AddressOrder**

Valid Values:

* Default
* Reversed






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |18      |false        |



#### **Birthday**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[datetime]`|false   |9       |false        |



#### **City**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |13      |false        |



#### **Country**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |15      |false        |



#### **Email**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |8       |false        |



#### **FilePath**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |0       |false        |



#### **Firstname**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |2       |false        |



#### **HouseNumber**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |12      |false        |



#### **Lastname**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |3       |false        |



#### **MobilePhone**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |6       |false        |



#### **Nickname**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |4       |false        |



#### **Note**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |16      |false        |



#### **Org**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |19      |false        |



#### **OrgTitle**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |20      |false        |



#### **Phone**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |5       |false        |



#### **Show**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **StateRegion**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |17      |false        |



#### **Street**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |11      |false        |



#### **Website**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |10      |false        |



#### **WorkPhone**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |7       |false        |



#### **ZipCode**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |14      |false        |



#### **outputType**

Valid Values:

* MeCard
* VCard21
* VCard3
* VCard4






|Type                                              |Required|Position|PipelineInput|
|--------------------------------------------------|--------|--------|-------------|
|`[PayloadGenerator+ContactData+ContactOutputType]`|false   |1       |false        |





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
{@{name=New-ImageQRContact; CommonParameters=True; parameter=System.Object[]}}
```
