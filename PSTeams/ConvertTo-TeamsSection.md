ConvertTo-TeamsSection
----------------------




### Synopsis
Convert an array of PSCustomObject or a Hashtable to separate Teams sections.



---


### Description

Teams sections are chunks of information that appear within a Teams message. This function helps convert an array of PSObject or an array of Hashtables to Teams sections (only one level deep).



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-ChildItem -Directory | ConvertTo-TeamsSection -SectionTitleProperty Name
```



---


### Parameters
#### **InputObject**

The Hashtable or PSObject that is output by another cmdlet.






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[Object]`|true    |1       |true (ByValue)|



#### **SectionTitleProperty**

The property to use for title






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |





---


### Notes
Ram Iyer (https://ramiyer.me)



---


### Syntax
```PowerShell
ConvertTo-TeamsSection [-InputObject] <Object> [[-SectionTitleProperty] <String>] [<CommonParameters>]
```
