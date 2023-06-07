New-CMInventoryReportClass
--------------------------




### Synopsis
{{ Fill in the Synopsis }}



---


### Description

{{ Fill in the Description }}



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> {{ Add example code here }}
```
{{ Add example description here }}


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



#### **Id**

{{ Fill Id Description }}






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |0       |False        |SMSClassID|



#### **InputObject**

{{ Fill InputObject Description }}






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|InventoryClass|



#### **Name**

{{ Fill Name Description }}






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |ClassName|



#### **ReportProperty**

{{ Fill ReportProperty Description }}






|Type        |Required|Position|PipelineInput|Aliases         |
|------------|--------|--------|-------------|----------------|
|`[String[]]`|false   |named   |False        |ReportProperties|



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
* IResultObject#SMS_InventoryReportClass






---


### Notes




---


### Syntax
```PowerShell
New-CMInventoryReportClass [-Id] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ReportProperty <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMInventoryReportClass [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-ReportProperty <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMInventoryReportClass [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-ReportProperty <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
