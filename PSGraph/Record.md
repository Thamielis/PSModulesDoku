Record
------




### Synopsis
Creates a record object



---


### Description

Creates a record object that contains rows of data.



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


    Echo one two three | Record Fish
    Record Cow red,blue,green

} | Export-PSGraph -ShowGraph


---


### Parameters
#### **Name**

The node name for this record






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |1       |false        |ID<br/>Node|



#### **Row**

An array of strings/objects to place in this record






|Type        |Required|Position|PipelineInput |Aliases|
|------------|--------|--------|--------------|-------|
|`[Object[]]`|false   |2       |true (ByValue)|Rows   |



#### **ScriptBlock**

A sub expression that contains Row commands






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ScriptBlock]`|false   |2       |false        |



#### **RowScript**

A script to run on each row






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ScriptBlock]`|false   |3       |false        |



#### **Label**

The label to use for the headder of the record.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |





---


### Outputs
* [String](https://learn.microsoft.com/en-us/dotnet/api/System.String)






---


### Notes
Early release version of this command.
A lot of stuff is hard coded that should be exposed as attributes



---


### Syntax
```PowerShell
Record [-Name] <String> [[-ScriptBlock] <ScriptBlock>] [[-RowScript] <ScriptBlock>] [-Label <String>] [<CommonParameters>]
```
```PowerShell
Record [-Name] <String> [[-Row] <Object[]>] [[-RowScript] <ScriptBlock>] [-Label <String>] [<CommonParameters>]
```
