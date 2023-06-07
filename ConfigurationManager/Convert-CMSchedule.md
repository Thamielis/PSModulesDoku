Convert-CMSchedule
------------------




### Synopsis
Converts schedule tokens into and from interval strings.



---


### Description

The Convert-CMSchedule cmdlet decodes and encodes schedule tokens into and from Configuration Manager interval strings.



In Configuration Manager, scheduling information is configured by using schedule tokens. The interval strings can be used to set schedule properties when defining or modifying objects.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMClientStatusUpdateSchedule](Get-CMClientStatusUpdateSchedule)



* [Get-CMBaselineSummarizationSchedule](Get-CMBaselineSummarizationSchedule)



* [Get-CMOperatingSystemImageUpdateSchedule](Get-CMOperatingSystemImageUpdateSchedule)



* [Get-CMEndpointProtectionSummarizationSchedule](Get-CMEndpointProtectionSummarizationSchedule)



* [Get-CMSoftwareUpdateSummarizationSchedule](Get-CMSoftwareUpdateSummarizationSchedule)



* [New-CMSchedule](New-CMSchedule)





---


### Examples
#### Example 1: Convert a schedule string
```PowerShell
PS XYZ:\>Convert-CMSchedule -ScheduleString "02C159C0381A200002C159C0381B200002C159C0381C200002C159C0381D200002C159C0381E2000"
```
This command converts a schedule string into a schedule token.


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



#### **InputObject**








|Type               |Required|Position|PipelineInput |Aliases      |
|-------------------|--------|--------|--------------|-------------|
|`[IResultObject[]]`|true    |0       |True (ByValue)|ScheduleToken|



#### **ScheduleString**

Specifies an array of interval strings.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |0       |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]





---


### Outputs
* IResultObject#SMS_ScheduleToken


* [String](https://learn.microsoft.com/en-us/dotnet/api/System.String)


* [String[]](https://learn.microsoft.com/en-us/dotnet/api/System.String[])






---


### Notes




---


### Syntax
```PowerShell
Convert-CMSchedule [-InputObject] <IResultObject[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Convert-CMSchedule [-ScheduleString] <String[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
