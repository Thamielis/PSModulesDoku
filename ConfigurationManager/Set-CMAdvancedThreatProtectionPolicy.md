Set-CMAdvancedThreatProtectionPolicy
------------------------------------




### Synopsis
Sets an advanced threat protection policy.



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








|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



#### **Digest**








|Type                 |Required|Position|PipelineInput |
|---------------------|--------|--------|--------------|
|`[ConfigurationItem]`|false   |named   |True (ByValue)|



#### **DigestPath**








|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|false   |named   |False        |DesiredConfigurationDigestPath|



#### **DigestXml**








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
|`[String]`|false   |named   |False        |ConfigurationFileLocation|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**








|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **NewName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Order**





Valid Values:

* Increase
* Decrease






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PriorityChangeType]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Microsoft.ConfigurationManagement.DesiredConfigurationManagement.ConfigurationItem



Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMAdvancedThreatProtectionPolicy [-InputObject] <IResultObject> [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-FilePath <String>] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-SampleSharingType {None | All}] [-TelemetryReportingFrequencyType {Normal | Expedited}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAdvancedThreatProtectionPolicy [-Id] <Int32> [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-FilePath <String>] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-SampleSharingType {None | All}] [-TelemetryReportingFrequencyType {Normal | Expedited}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAdvancedThreatProtectionPolicy [-Name] <String> [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-FilePath <String>] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-SampleSharingType {None | All}] [-TelemetryReportingFrequencyType {Normal | Expedited}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAdvancedThreatProtectionPolicy [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -Order {Increase | Decrease} [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAdvancedThreatProtectionPolicy [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -Order {Increase | Decrease} [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAdvancedThreatProtectionPolicy [-Name] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -Order {Increase | Decrease} [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
