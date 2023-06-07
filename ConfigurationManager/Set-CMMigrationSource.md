Set-CMMigrationSource
---------------------




### Synopsis
Specifies or changes settings for a migration source site in Configuration Manager.



---


### Description

The Set-CMMigrationSource cmdlet specifies or changes settings for a migration source site in Configuration Manager. To enable migration of data to your Configuration Manager environment, you must configure a supported Configuration Manager source hierarchy and specify one or more source sites that contain data that you want to migrate.



By default, the top-level site of the hierarchy becomes a source site of the source hierarchy. If you migrate from a Configuration Manager 2007 hierarchy, you can configure additional source sites for migration. If you migrate from a Configuration Manager hierarchy, you do not need to configure additional source sites because the Configuration Manager shared database at the top of the source hierarchy contains all of the information that you can migrate.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMMigrationExclusionList](Set-CMMigrationExclusionList)



* [Clear-CMMigrationData](Clear-CMMigrationData)





---


### Examples
#### Example 1: Specify a migration source
```PowerShell
PS XYZ:\> Set-CMMigrationSource -SourceSiteServerName "cmdev-contoso01" -SmsProviderAccount "tsqa\pattifuller" -SqlServerAccount "tsqa\pattifuller" -EnableDistributionPointSharing $True
```
This command specifies the site server named cmdev-contoso01 as the source of migration data. It uses the user account for tsqa\pattifuller to provide access to the SQL Server database at the top of the source hierarchy and to connect to the SMS provider and source site database for the source site. The command also shares distribution points between the source and destination hierarchies.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableDistributionPointSharing**

Indicates whether Configuration Manager shares distribution points between source and destination hierarchies.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SmsProviderAccount**

Specifies the name of the account that the top-level site in the destination hierarchy uses to connect to the SMS Provider and the site database of the source site. The top-level site uses these connections to retrieve objects and distribution points.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SourceSiteServerName**

Specifies the name of a server that contains a source site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SqlServerAccount**

Specifies a SQL Server account that provides access to the top-level SQL Server database in the source hierarchy. The account must have read and run permissions for this database.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMMigrationSource [-DisableWildcardHandling] [-EnableDistributionPointSharing <Boolean>] [-ForceWildcardHandling] [-SmsProviderAccount <String>] -SourceSiteServerName <String> [-SqlServerAccount <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
