New-CMSoftwareMeteringRule
--------------------------




### Synopsis
Creates a Configuration Manager software metering rule.



---


### Description

The New-CMSoftwareMeteringRule cmdlet creates a Configuration Manager software metering rule. A software metering rule specifies a piece of software, along with version information. You can obtain necessary file information from Windows Explorer.



Software metering monitors and collects software usage data from Configuration Manager clients, such as when clients began using a particular software program and how long users have worked with that software. You can create software metering rules that specify which software to monitor.



For more information about software metering in Configuration Manager, see Introduction to Software Metering in Configuration Manager (/mem/configmgr/apps/deploy-use/monitor-app-usage-with-software-metering).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMSoftwareMeteringRule](Disable-CMSoftwareMeteringRule)



* [Enable-CMSoftwareMeteringRule](Enable-CMSoftwareMeteringRule)



* [Get-CMSoftwareMeteringRule](Get-CMSoftwareMeteringRule)



* [Remove-CMSoftwareMeteringRule](Remove-CMSoftwareMeteringRule)



* [Set-CMSoftwareMeteringRule](Set-CMSoftwareMeteringRule)





---


### Examples
#### Example 1: Create a software metering rule
```PowerShell
PS XYZ:\> New-CMSoftwareMeteringRule -Path "Notepad.exe" -SiteCode "CM1" -FileVersion "6.1.7600.16385" -OriginalFileName "NOTEPAD.EXE" -ProductName "Microsoft Windows Operating System"
ApplyToChildSites : True
Comment           :
Enabled           : True
FileName          : Notepad.exe
FileVersion       : 6.1.7600.16385
LanguageID        :
LastUpdateTime    :
OriginalFileName  : NOTEPAD.EXE
ProductName       : Microsoft Windows Operating System
RuleID            :
SecurityKey       :
SiteCode          : CM1
SourceSite        :
```
This command creates a software metering rule for the Configuration Manager site named CM1. The command specifies the file name, version, original file name, and product name for the software product.


---


### Parameters
#### **Comment**

Specifies a comment for a software metering rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FileVersion**

Specifies a version of the software that a rule meters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **LanguageId**

Specifies a LocaleID of the software that a rule meters. For more information and a list of locale identifiers, see Appendix A: Product Behavior (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **OriginalFileName**

Specifies an original file name of the software that a rule meters. This parameter can differ from the Path parameter if a user changed the name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Path**

Specifies a file path of the software that a rule meters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ProductName**

Specifies a name for a product that a rule meters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SiteCode**

Specifies a site code for a Configuration Manager site.






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
None





---


### Outputs
* IResultObject#SMS_MeteredProductRule






---


### Notes




---


### Syntax
```PowerShell
New-CMSoftwareMeteringRule [-Comment <String>] [-DisableWildcardHandling] [-FileName <String>] [-FileVersion <String>] [-ForceWildcardHandling] [-LanguageId <Int32>] [-OriginalFileName <String>] -ProductName <String> [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareMeteringRule [-DisableWildcardHandling] [-ForceWildcardHandling] -Path <String> [-ProductName <String>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
