Set-CMSoftwareUpdate
--------------------




### Synopsis
Sets a software update.



---


### Description

The Set-CMSoftwareUpdate cmdlet changes configuration settings for a software update. You can use this cmdlet to set the severity and the maximum run time for an update. A software update is an update to Windows or other software that Configuration Manager applies to a collection of computers.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate)



* [Save-CMSoftwareUpdate](Save-CMSoftwareUpdate)



* [Sync-CMSoftwareUpdate](Sync-CMSoftwareUpdate)





---


### Examples
#### Example 1: Get a software update and change its settings
```PowerShell
PS XYZ:\> Get-CMSoftwareUpdate -Name "Update for Windows 10 (KB3106932)" | Set-CMSoftwareUpdate -MaximumExecutionMins 10 -CustomSeverity Critical
```
This command gets the software update object named Update for Windows 10 (KB3106932) and uses the pipeline operator to pass the object to Set-CMSoftwareUpdate , which sets the severity of the update to Critical and the maximum installation time to 10 minutes.
#### Example 2: Modify software update settings
```PowerShell
PS XYZ:\> Set-CMSoftwareUpdate -Id 16777979 -MaximumExecutionMins 10 -CustomSeverity Critical
```
This command gets the software update with the ID of 16777979 and sets the severity of the update to Critical and the maximum installation time to 10 minutes.


---


### Parameters
#### **CustomSeverity**

Specifies the severity for the software update. Valid values are:


* Critical


* Important


* Low


* Moderate


* None



Valid Values:

* None
* Low
* Moderate
* Important
* Critical






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[CustomSeverityType]`|false   |named   |False        |



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

Specifies the ID of software updates.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a software update object. To obtain a software update object, use the Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **MaximumExecutionMins**

Specifies, in minutes, the maximum amount of time that a software update has to complete installation on client computers.






|Type     |Required|Position|PipelineInput|Aliases                |
|---------|--------|--------|-------------|-----------------------|
|`[Int32]`|false   |named   |False        |MaximumExecutionMinutes|



#### **Name**

Specifies the name of a software update.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



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
Set-CMSoftwareUpdate [-CustomSeverity {None | Low | Moderate | Important | Critical}] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-MaximumExecutionMins <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdate [-CustomSeverity {None | Low | Moderate | Important | Critical}] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-MaximumExecutionMins <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdate [-CustomSeverity {None | Low | Moderate | Important | Critical}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaximumExecutionMins <Int32>] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
