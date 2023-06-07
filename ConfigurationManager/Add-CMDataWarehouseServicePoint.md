Add-CMDataWarehouseServicePoint
-------------------------------




### Synopsis
Adds a data warehouse service point



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



---


### Parameters
#### **DataRetentionDays**

{{ Fill DataRetentionDays Description }}






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DataWarehouseDatabaseName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DataWarehouseDatabaseServerName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DataWarehouseInstanceName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DataWarehouseSqlPort**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DaysOfWeek**





Valid Values:

* Sunday
* Monday
* Tuesday
* Wednesday
* Thursday
* Friday
* Saturday
* Daily






|Type                       |Required|Position|PipelineInput|
|---------------------------|--------|--------|-------------|
|`[DataWarehouseDaysOfWeek]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteServer|



#### **SiteCode**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**








|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **StartAftertime**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **UserName**

{{ Fill UserName Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **WeekFrequency**








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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Add-CMDataWarehouseServicePoint [-DataRetentionDays <Int32>] [-DataWarehouseDatabaseName <String>] [-DataWarehouseDatabaseServerName <String>] [-DataWarehouseInstanceName <String>] [-DataWarehouseSqlPort <Int32>] [-DaysOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday | Daily}] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-StartAftertime <DateTime>] -UserName <String> [-WeekFrequency <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDataWarehouseServicePoint [-SiteSystemServerName] <String> [-DataRetentionDays <Int32>] [-DataWarehouseDatabaseName <String>] [-DataWarehouseDatabaseServerName <String>] [-DataWarehouseInstanceName <String>] [-DataWarehouseSqlPort <Int32>] [-DaysOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday | Daily}] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-StartAftertime <DateTime>] -UserName <String> [-WeekFrequency <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
