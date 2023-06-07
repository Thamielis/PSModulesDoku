New-CMSqlServerSetting
----------------------




### Synopsis
Creates a SQL Server settings object in Configuration Manager.



---


### Description

The New-CMSqlServerSetting cmdlet creates a Microsoft SQL Server settings object in Configuration Manager. The object specifies settings for the name of the site database and the port number for the SQL Server service and SQL Server Service Broker.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Create a SQL Server settings object
```PowerShell
PS XYZ:\> New-CMSqlServerSetting -CopySqlServerExpressOnSecondarySite -SqlServerServiceBrokerPort 4037
```
This command creates a SQL Server settings object that specifies that Configuration Manager copies Microsoft SQL Server Express to a secondary site. The command specifies that Configuration Manager use port 4037 for the SQL Server Service Broker.


---


### Parameters
#### **CopySqlServerExpressOnSecondarySite**

Indicates that Microsoft SQL Server Express is copied to a secondary site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



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



#### **InstanceName**

Specifies the name of an instance of SQL Server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteDatabaseName**

Specifies a name of the Configuration Manager site database.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SqlServerServiceBrokerPort**

Specifies a port number for the SQL Server Service Broker port.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SqlServerServicePort**

Specifies a port number for the SQL Server service port.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UseExistingSqlServerInstance**

Indicates that you use the existing instance of SQL Server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



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
* IResultObject#SMS_EmbeddedProperty


* IResultObject[]#SMS_EmbeddedProperty






---


### Notes




---


### Syntax
```PowerShell
New-CMSqlServerSetting -CopySqlServerExpressOnSecondarySite [-DisableWildcardHandling] [-ForceWildcardHandling] [-SqlServerServiceBrokerPort <Int32>] [-SqlServerServicePort <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSqlServerSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-InstanceName <String>] -SiteDatabaseName <String> [-SqlServerServiceBrokerPort <Int32>] -UseExistingSqlServerInstance [-Confirm] [-WhatIf] [<CommonParameters>]
```
