New-CMAdvancedThreatProtectionPolicy
------------------------------------




### Synopsis
Creates an advanced threat protection policy.



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
#### **Description**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FilePath**








|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|true    |named   |False        |ConfigurationFileLocation|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PolicyType**





Valid Values:

* Offboarding
* Onboarding






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[ConfigurationType]`|true    |named   |False        |



#### **SampleSharingType**





Valid Values:

* None
* All






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[SampleSharingType]`|false   |named   |False        |



#### **TelemetryReportingFrequencyType**





Valid Values:

* None
* Normal
* Expedited






|Type                               |Required|Position|PipelineInput|
|-----------------------------------|--------|--------|-------------|
|`[TelemetryReportingFrequencyType]`|false   |named   |False        |



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
* IResultObject#SMS_ConfigurationPolicy






---


### Notes




---


### Syntax
```PowerShell
New-CMAdvancedThreatProtectionPolicy [-Description <String>] [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] -Name <String> -PolicyType {Onboarding | Offboarding} [-SampleSharingType {None | All}] [-TelemetryReportingFrequencyType {Normal | Expedited}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
