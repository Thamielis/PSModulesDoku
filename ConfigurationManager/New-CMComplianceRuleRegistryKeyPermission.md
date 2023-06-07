New-CMComplianceRuleRegistryKeyPermission
-----------------------------------------




### Synopsis
Creates a compliance rule registry key permission.



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
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExpectedPermission**





Valid Values:

* None
* QueryValue
* SetValue
* CreateSubkey
* EnumerateSubkeys
* Notify
* CreateLink
* Delete
* ReadPermissions
* Write
* Read
* ChangePermissions
* TakeOwnership
* FullControl






|Type                     |Required|Position|PipelineInput|Aliases            |
|-------------------------|--------|--------|-------------|-------------------|
|`[RegistryPermissions[]]`|true    |named   |False        |ExpectedPermissions|



#### **ExpectedUserAccess**








|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type                        |Required|Position|PipelineInput |Aliases|
|----------------------------|--------|--------|--------------|-------|
|`[ConfigurationItemSetting]`|true    |named   |True (ByValue)|Setting|



#### **IsExclusive**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **NoncomplianceSeverity**





Valid Values:

* None
* Informational
* Warning
* Critical
* CriticalWithEvent






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[NoncomplianceSeverity]`|false   |named   |False        |



#### **ReportNoncompliance**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RuleDescription**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RuleName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Microsoft.ConfigurationManagement.DesiredConfigurationManagement.ConfigurationItemSetting





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMComplianceRuleRegistryKeyPermission [-DisableWildcardHandling] -ExpectedPermission {None | QueryValue | SetValue | CreateSubkey | EnumerateSubkeys | Notify | CreateLink | Delete | ReadPermissions | Write | Read | ChangePermissions | TakeOwnership | FullControl} -ExpectedUserAccess <Hashtable> [-ForceWildcardHandling] -InputObject <ConfigurationItemSetting> [-IsExclusive <Boolean>] [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] [-ReportNoncompliance] [-RuleDescription <String>] -RuleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
