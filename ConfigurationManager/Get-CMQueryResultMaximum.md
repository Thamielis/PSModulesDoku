Get-CMQueryResultMaximum
------------------------




### Synopsis
Gets the maximum number of rows that a Configuration Manager report query can return.



---


### Description

The Get-CMQueryResultMaximum cmdlet gets the maximum number of rows that a Configuration Manager query can return. By default, queries in Configuration Manager return only a subset of the matching rows in the database. This cmdlet indicates the number of rows that Configuration Manager returns. To change the maximum number of rows that a Configuration Manager query returns, use the Set-CMQueryResultMaximum (Set-CMQueryResultMaximum.md)cmdlet. By default, the maximum number of rows is unbound, which is different from the behavior of the Configuration Manager console, and is also different from earlier releases of the Configuration Manager cmdlet library.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMQueryResultMaximum](Set-CMQueryResultMaximum)





---


### Examples
#### Example 1: Get the report query result maximum
```PowerShell
PS XYZ:\> Get-CMQueryResultMaximum
```
This command gets the maximum number of rows that a Configuration Manager report query can return.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* [Int32](https://learn.microsoft.com/en-us/dotnet/api/System.Int32)






---


### Notes




---


### Syntax
```PowerShell
Get-CMQueryResultMaximum [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
