Set-CMComplianceSettingSqlQuery
-------------------------------




### Synopsis
Sets a compliance setting sql query.



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
#### **ColumnName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DatabaseName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Description**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **InputObject**








|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[PSObject]`|true    |named   |True (ByValue)|



#### **InstanceName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InstanceType**





Valid Values:

* Default
* Named
* All






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[TargetSqlInstance]`|false   |named   |False        |



#### **NewSettingName**








|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |NewName|



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SettingName**








|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **SqlStatementFile**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SqlStatementText**








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
System.Management.Automation.PSObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMComplianceSettingSqlQuery [-ColumnName <String>] [-DatabaseName <String>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <PSObject> [-InstanceName <String>] [-InstanceType {All | Default | Named}] [-NewSettingName <String>] [-PassThru] -SettingName <String> [-SqlStatementFile <String>] [-SqlStatementText <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```