Entity
------




### Synopsis
Convert an object into a PSGraph Record



---


### Description

Convert an object into a PSGraph Record



---


### Examples
#### EXAMPLE 1
```PowerShell
$sample = [pscustomobject]@{
    first = 1
    second = 'two'
}
graph {
    $sample |  Entity -Show TypeName
} | export-PSGraph -ShowGraph
```



---


### Parameters
#### **InputObject**

The object to convert into a record






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[Object]`|false   |1       |true (ByValue)|



#### **Name**

The name of the node






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Property**

The list of properties to display. Default is to list them all.
Supports wildcards.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |false        |



#### **Show**

The different details to show in the record.

Name : The property name
Value : The property name and value
TypeName : The property name and the value type



Valid Values:

* Name
* Value
* TypeName






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[EntityType]`|false   |named   |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Entity [[-InputObject] <Object>] [-Name <String>] [-Property <String[]>] [-Show {Name | Value | TypeName}] [<CommonParameters>]
```
