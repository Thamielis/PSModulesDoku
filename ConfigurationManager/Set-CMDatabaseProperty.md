Set-CMDatabaseProperty
----------------------




### Synopsis
Changes database settings for a Configuration Manager database.



---


### Description

The Set-CMDatabaseProperty cmdlet changes database settings for a Configuration Manager site database. Specify the Configuration Manager site code for the database that you want to modify.



You can modify whether the database uses data compression, the Service Broker port for the computer that runs Microsoft SQL Server, and the length of time that the database keeps data. You can use the Get-CMDatabaseProperty (Get-CMDatabaseProperty.md)cmdlet to see current values for these properties.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDatabaseProperty](Get-CMDatabaseProperty)





---


### Examples
#### Example 1: Change settings for a database
```PowerShell
PS XYZ:\> Set-CMDatabaseProperty -SiteCode "CM2" -DataRetentionPeriodDays 10 -EnableDataCompression $False -SqlServerServiceBrokerPort 80
```
This command makes changes to the database for the site that has the site code CM2. The command sets the data retention period to 10 days, disables data compression, and specifies a port for the SQL Server Service Broker.


---


### Parameters
#### **DataRetentionDays**








|Type     |Required|Position|PipelineInput|Aliases                |
|---------|--------|--------|-------------|-----------------------|
|`[Int32]`|false   |named   |False        |DataRetentionPeriodDays|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableDataCompression**

Specifies whether the database uses data compression.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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



#### **SqlServerServiceBrokerPort**

Specifies the port that the computer running SQL Server uses as a Service Broker port.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMDatabaseProperty [-DataRetentionDays <Int32>] [-DisableWildcardHandling] [-EnableDataCompression <Boolean>] [-ForceWildcardHandling] [-SiteCode <String>] [-SqlServerServiceBrokerPort <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
