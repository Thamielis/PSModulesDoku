New-ImageBarCode
----------------




### Synopsis

New-ImageBarCode [-Type] <BarCode+BarcodeTypes> [-Value] <string> [-FilePath] <string> [<CommonParameters>]




---


### Description


---


### Parameters
#### **FilePath**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |2       |false        |



#### **Type**

Valid Values:

* Code128
* Code93
* Code39
* KixCode
* UPCE
* UPCA
* EAN






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[BarCode+BarcodeTypes]`|true    |0       |false        |



#### **Value**




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
{@{name=New-ImageBarCode; CommonParameters=True; parameter=System.Object[]}}
```
