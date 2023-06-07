Set-CMClientSettingEnrollment
-----------------------------




### Synopsis
Sets a client setting enrollment.



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
#### **DefaultSetting**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableDevice**








|Type       |Required|Position|PipelineInput|Aliases               |
|-----------|--------|--------|-------------|----------------------|
|`[Boolean]`|false   |named   |False        |EnableDeviceEnrollment|



#### **EnableModernDevice**








|Type       |Required|Position|PipelineInput|Aliases                     |
|-----------|--------|--------|-------------|----------------------------|
|`[Boolean]`|false   |named   |False        |EnableModernDeviceEnrollment|



#### **EnrollmentProfileName**








|Type      |Required|Position|PipelineInput|Aliases                                                          |
|----------|--------|--------|-------------|-----------------------------------------------------------------|
|`[String]`|false   |named   |False        |DeviceEnrollmentProfileName<br/>MobileDeviceEnrollmentProfileName|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **IntervalDeviceHr**








|Type     |Required|Position|PipelineInput|Aliases                     |
|---------|--------|--------|-------------|----------------------------|
|`[Int32]`|false   |named   |False        |PollingIntervalForDeviceHour|



#### **IntervalDeviceMins**








|Type     |Required|Position|PipelineInput|Aliases                        |
|---------|--------|--------|-------------|-------------------------------|
|`[Int32]`|false   |named   |False        |PollingIntervalForDeviceMinutes|



#### **IntervalModernMins**








|Type     |Required|Position|PipelineInput|Aliases                              |
|---------|--------|--------|-------------|-------------------------------------|
|`[Int32]`|false   |named   |False        |PollingIntervalForModernDeviceMinutes|



#### **ModernEnrollmentProfileName**








|Type      |Required|Position|PipelineInput|Aliases                          |
|----------|--------|--------|-------------|---------------------------------|
|`[String]`|false   |named   |False        |ModernDeviceEnrollmentProfileName|



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Set-CMClientSettingEnrollment -DefaultSetting [-DisableWildcardHandling] [-EnableDevice <Boolean>] [-EnableModernDevice <Boolean>] [-EnrollmentProfileName <String>] [-ForceWildcardHandling] [-IntervalDeviceHr <Int32>] [-IntervalDeviceMins <Int32>] [-IntervalModernMins <Int32>] [-ModernEnrollmentProfileName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingEnrollment [-DisableWildcardHandling] [-EnableDevice <Boolean>] [-EnableModernDevice <Boolean>] [-EnrollmentProfileName <String>] [-ForceWildcardHandling] -InputObject <IResultObject> [-IntervalDeviceHr <Int32>] [-IntervalDeviceMins <Int32>] [-IntervalModernMins <Int32>] [-ModernEnrollmentProfileName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingEnrollment [-DisableWildcardHandling] [-EnableDevice <Boolean>] [-EnableModernDevice <Boolean>] [-EnrollmentProfileName <String>] [-ForceWildcardHandling] [-IntervalDeviceHr <Int32>] [-IntervalDeviceMins <Int32>] [-IntervalModernMins <Int32>] [-ModernEnrollmentProfileName <String>] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
