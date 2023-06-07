Get-CMDatabaseProperty
----------------------




### Synopsis
Gets an object that represents a Configuration Manager database.



---


### Description

The Get-CMDatabaseProperty cmdlet gets an object that represents a Configuration Manager database. Use the site code for a site to specify a database.



When this cmdlet returns a database object in the console, it displays current settings for data compression, Broker port for the computer that runs Microsoft SQL Server, and the length of time that the database keeps data. You can use the Set-CMDatabaseProperty (Set-CMDatabaseProperty.md)cmdlet to change these values.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMDatabaseProperty](Set-CMDatabaseProperty)





---


### Examples
#### Example 1: Get a database property
```PowerShell
PS XYZ:\> Get-CMDatabaseProperty -SiteCode "CM2"
Key                                     Value
---                                     -----
SQL Server Service Broker Port          80
Retention Period                        10
IsCompression                           0
```
This command gets the database property for the site that has the site code CM2.


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



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* Dictionary<string, object>






---


### Notes




---


### Syntax
```PowerShell
Get-CMDatabaseProperty [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
