Row
---




### Synopsis
Adds a row to a record



---


### Description

Adds a row to a record inside a PSGraph Graph



---


### Examples
#### EXAMPLE 1
```PowerShell
graph {
```
Record Components1 @(
        'Name'
        'Environment'
        'Test <I>[string]</I>'
    )

    Record Components2 {
        Row Name
        Row 'Environment <B>test</B>'
        'Test'
    }


    Edge Components1:Name -to Components2:Name

} | Export-PSGraph -ShowGraph


---


### Parameters
#### **Label**

This is the displayed data for the row






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[String]`|true    |1       |true (ByValue)|



#### **Name**

This is the target name of this row to be used in edges.
Will default to the label if the label has not special characters






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |false        |ID     |



#### **HtmlEncode**

This will encode unintentional HTML. Characters like <>& would break html parsing if they are
contained in the source data.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Outputs
* [String](https://learn.microsoft.com/en-us/dotnet/api/System.String)






---


### Notes
Need to add attribute support

DSL planned syntax
# Row Label
# Row Label -ID
# Row Label Attributes
# Row Label -ID Attributes



---


### Syntax
```PowerShell
Row [-Label] <String> [-Name <String>] [-HtmlEncode] [<CommonParameters>]
```
