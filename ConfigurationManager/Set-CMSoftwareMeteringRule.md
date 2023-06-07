Set-CMSoftwareMeteringRule
--------------------------




### Synopsis
Changes properties and security scopes for Configuration Manager software metering rules.



---


### Description

The Set-CMSoftwareMeteringRule cmdlet changes properties for software metering rules in Configuration Manager and adds or removes security scopes for software metering rules. Every rule must have at least one security scope.



Software metering monitors and collects software usage data from Configuration Manager clients, such as when clients began using a particular software program and how long users have worked with that software. You can create software metering rules that specify which software to monitor.



To change rule properties, you can specify rules to change by ID or by product name, or use the Get-CMSoftwareMeteringRule (Get-CMSoftwareMeteringRule.md)cmdlet. Likewise, you can change security scope for rules for specified ID, product name, or by using Get-CMSoftwareMeteringRule .



For more information about software metering in Configuration Manager, see Introduction to Software Metering in Configuration Manager (/mem/configmgr/apps/deploy-use/monitor-app-usage-with-software-metering). For more information about security scopes, see Planning for Security in Configuration Manager (/mem/configmgr/core/plan-design/security/plan-for-security).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMSoftwareMeteringRule](Disable-CMSoftwareMeteringRule)



* [Enable-CMSoftwareMeteringRule](Enable-CMSoftwareMeteringRule)



* [Get-CMSoftwareMeteringRule](Get-CMSoftwareMeteringRule)



* [New-CMSoftwareMeteringRule](New-CMSoftwareMeteringRule)



* [Remove-CMSoftwareMeteringRule](Remove-CMSoftwareMeteringRule)





---


### Examples
#### Example 1: Change locale for rules for a product
```PowerShell
PS XYZ:\> Set-CMSoftwareMeteringRule -ProductName "Accounting Package" -LanguageID 1036
```
This command sets the locale ID for rules that include the product name Accounting Package.
#### Example 2: Add a security scope to rules for a product
```PowerShell
PS XYZ:\> Set-CMSoftwareMeteringRule -ProductName "Accounting Package" -SecurityScopeAction AddMembership -SecurityScopeName "Scope05"
```
This command adds the security scope called Scope05 to rules for the product name Accounting Package.


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

Specifies the filename of the software that a rule meters.






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



#### **Id**

Specifies an array of IDs for software metering rules.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |RuleId |



#### **InputObject**

Specifies a software metering rule object. To obtain a software metering rule object, use the Get-CMSoftwareMeteringRule (Get-CMSoftwareMeteringRule.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **LanguageId**

Specifies a LocaleID of the software that a rule meters. For more information and a list of locale identifiers, see Appendix A: Product Behavior (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **NewProductName**

Specifies a new name for the software that a rule meters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OriginalFileName**

Specifies an original file name of the software that a rule meters. This parameter can differ from the FileName parameter if a user changed the name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

Specifies a file path of the software that a rule meters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ProductName**

Specifies a name for a product that a rule meters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SiteCode**

Specifies a site code of a Configuration Manager site.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMSoftwareMeteringRule [-Comment <String>] [-DisableWildcardHandling] [-FileName <String>] [-FileVersion <String>] [-ForceWildcardHandling] -Id <String> [-LanguageId <Int32>] [-NewProductName <String>] [-OriginalFileName <String>] [-PassThru] [-Path <String>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareMeteringRule [-Comment <String>] [-DisableWildcardHandling] [-FileName <String>] [-FileVersion <String>] [-ForceWildcardHandling] -InputObject <IResultObject> [-LanguageId <Int32>] [-NewProductName <String>] [-OriginalFileName <String>] [-PassThru] [-Path <String>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareMeteringRule [-Comment <String>] [-DisableWildcardHandling] [-FileName <String>] [-FileVersion <String>] [-ForceWildcardHandling] [-LanguageId <Int32>] [-NewProductName <String>] [-OriginalFileName <String>] [-PassThru] [-Path <String>] -ProductName <String> [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
