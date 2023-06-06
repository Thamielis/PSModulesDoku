ConvertTo-TeamsFact
-------------------




### Synopsis
Convert a PSCustomObject or a Hashtable to Teams facts.



---


### Description

Teams facts are name-value pairs. This function helps convert a PSObject or a Hashtable to Teams facts (only one level deep).



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-ChildItem | Select-Object -First 1 | ConvertTo-TeamsFact
```

#### EXAMPLE 2
```PowerShell
@{ Product = 'Microsoft Teams'; Developer = 'Microsoft Corporation'; ReleaseYear = '2018' } | ConvertTo-TeamsFact
```



---


### Parameters
#### **InputObject**

The Hashtable or PSObject that is output by another cmdlet.






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[Object]`|true    |1       |true (ByValue)|





---


### Notes
Ram Iyer (https://ramiyer.me)



---


### Syntax
```PowerShell
ConvertTo-TeamsFact [-InputObject] <Object> [<CommonParameters>]
```
