Set-CMClientSettingWindowsAnalytics
-----------------------------------




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
#### **CommercialIdKey**

{{ Fill CommercialIdKey Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DefaultSetting**

{{ Fill DefaultSetting Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Enable**

{{ Fill Enable Description }}






|Type       |Required|Position|PipelineInput|Aliases                         |
|-----------|--------|--------|-------------|--------------------------------|
|`[Boolean]`|false   |named   |False        |EnableWindowsAnalyticsManagement|



#### **EnableEarlierTelemetry**

{{ Fill EnableEarlierTelemetry Description }}






|Type       |Required|Position|PipelineInput|Aliases                           |
|-----------|--------|--------|-------------|----------------------------------|
|`[Boolean]`|false   |named   |False        |EnableWindows81AndEarlierTelemetry|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IEDataCollectionOption**

{{ Fill IEDataCollectionOption Description }}



Valid Values:

* Disable
* LocalIntranetAndTrustedSitesAndMachineLocal
* InternetAndRestrictedSites
* AllZones






|Type                                  |Required|Position|PipelineInput|Aliases                                                   |
|--------------------------------------|--------|--------|-------------|----------------------------------------------------------|
|`[InternetExplorerTelemetryLevelType]`|false   |named   |False        |EnableWindows81AndEarlierInternetExplorerDataCollectionFor|



#### **InputObject**

{{ Fill InputObject Description }}






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

{{ Fill Name Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Win10Telemetry**

{{ Fill Win10Telemetry Description }}



Valid Values:

* None
* Basic
* Enhanced
* Full
* EnhancedLimited






|Type                       |Required|Position|PipelineInput|Aliases           |
|---------------------------|--------|--------|-------------|------------------|
|`[Win10TelemetryLevelType]`|false   |named   |False        |Windows10Telemetry|



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMClientSettingWindowsAnalytics [-CommercialIdKey <String>] -DefaultSetting [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableEarlierTelemetry <Boolean>] [-ForceWildcardHandling] [-IEDataCollectionOption {Disable | LocalIntranetAndTrustedSitesAndMachineLocal | InternetAndRestrictedSites | AllZones}] [-PassThru] [-Win10Telemetry {Basic | EnhancedLimited | Enhanced | Full}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingWindowsAnalytics [-CommercialIdKey <String>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableEarlierTelemetry <Boolean>] [-ForceWildcardHandling] [-IEDataCollectionOption {Disable | LocalIntranetAndTrustedSitesAndMachineLocal | InternetAndRestrictedSites | AllZones}] -InputObject <IResultObject> [-PassThru] [-Win10Telemetry {Basic | EnhancedLimited | Enhanced | Full}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingWindowsAnalytics [-CommercialIdKey <String>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableEarlierTelemetry <Boolean>] [-ForceWildcardHandling] [-IEDataCollectionOption {Disable | LocalIntranetAndTrustedSitesAndMachineLocal | InternetAndRestrictedSites | AllZones}] -Name <String> [-PassThru] [-Win10Telemetry {Basic | EnhancedLimited | Enhanced | Full}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
