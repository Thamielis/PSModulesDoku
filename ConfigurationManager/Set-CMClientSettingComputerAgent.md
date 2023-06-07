Set-CMClientSettingComputerAgent
--------------------------------




### Synopsis
Sets a client setting computer agent.



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
#### **AddPortalToTrustedSiteList**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowPortalToHaveElevatedTrust**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **BrandingTitle**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DefaultSetting**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableDeadlineRandom**








|Type       |Required|Position|PipelineInput|Aliases                     |
|-----------|--------|--------|-------------|----------------------------|
|`[Boolean]`|false   |named   |False        |DisableDeadlineRandomization|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisplayNewProgramNotification**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableHealthAttestation**








|Type       |Required|Position|PipelineInput|Aliases                       |
|-----------|--------|--------|-------------|------------------------------|
|`[Boolean]`|false   |named   |False        |EnableHealthAttestationService|



#### **EnableThirdPartyOrchestration**





Valid Values:

* No
* Yes






|Type                                 |Required|Position|PipelineInput|
|-------------------------------------|--------|--------|-------------|
|`[EnableThirdPartyOrchestrationType]`|false   |named   |False        |



#### **FinalReminderMins**








|Type     |Required|Position|PipelineInput|Aliases                                              |
|---------|--------|--------|-------------|-----------------------------------------------------|
|`[Int32]`|false   |named   |False        |FinalReminderMinutesInterval<br/>FinalReminderMinutes|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **HealthAttestationUrl**








|Type      |Required|Position|PipelineInput|Aliases                              |
|----------|--------|--------|-------------|-------------------------------------|
|`[String]`|false   |named   |False        |OnPremisesHealthAttestationServiceUrl|



#### **InitialReminderHr**








|Type     |Required|Position|PipelineInput|Aliases                                              |
|---------|--------|--------|-------------|-----------------------------------------------------|
|`[Int32]`|false   |named   |False        |InitialReminderHoursInterval<br/>InitialReminderHours|



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **InstallRestriction**





Valid Values:

* AllUsers
* OnlyAdministrators
* OnlyAdministratorsAndPrimaryUsers
* NoUsers






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[InstallRestrictionType]`|false   |named   |False        |



#### **InterimReminderHr**








|Type     |Required|Position|PipelineInput|Aliases                                              |
|---------|--------|--------|-------------|-----------------------------------------------------|
|`[Int32]`|false   |named   |False        |InterimReminderHoursInterval<br/>InterimReminderHours|



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PortalUrl**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PowerShellExecutionPolicy**





Valid Values:

* AllSigned
* Bypass
* Restricted






|Type                             |Required|Position|PipelineInput|
|---------------------------------|--------|--------|-------------|
|`[PowerShellExecutionPolicyType]`|false   |named   |False        |



#### **SelectWebsitePoint**

Don't use this parameter. The application catalog is no longer supported.



Valid Values:

* Fqdn
* AutoDetect
* NetBios






|Type                                  |Required|Position|PipelineInput|Aliases                             |
|--------------------------------------|--------|--------|-------------|------------------------------------|
|`[ApplicationCatalogWebsitePointType]`|false   |named   |False        |SelectApplicationCatalogWebsitePoint|



#### **SuspendBitLocker**





Valid Values:

* Never
* Always






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[SuspendBitLockerType]`|false   |named   |False        |



#### **UseNewSoftwareCenter**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseOnPremisesHealthAttestation**








|Type       |Required|Position|PipelineInput|Aliases                              |
|-----------|--------|--------|-------------|-------------------------------------|
|`[Boolean]`|false   |named   |False        |UseOnPremisesHealthAttestationService|



#### **WebsitePointServerName**








|Type      |Required|Position|PipelineInput|Aliases                                 |
|----------|--------|--------|-------------|----------------------------------------|
|`[String]`|false   |named   |False        |ApplicationCatalogWebsitePointServerName|



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
Set-CMClientSettingComputerAgent [-AddPortalToTrustedSiteList <Boolean>] [-AllowPortalToHaveElevatedTrust <Boolean>] [-BrandingTitle <String>] -DefaultSetting [-DisableDeadlineRandom <Boolean>] [-DisableWildcardHandling] [-DisplayNewProgramNotification <Boolean>] [-EnableHealthAttestation <Boolean>] [-EnableThirdPartyOrchestration {No | Yes}] [-FinalReminderMins <Int32>] [-ForceWildcardHandling] [-HealthAttestationUrl <String>] [-InitialReminderHr <Int32>] [-InstallRestriction {AllUsers | OnlyAdministrators | OnlyAdministratorsAndPrimaryUsers | NoUsers}] [-InterimReminderHr <Int32>] [-PassThru] [-PortalUrl <String>] [-PowerShellExecutionPolicy {AllSigned | Bypass | Restricted}] [-SelectWebsitePoint {Fqdn | AutoDetect | NetBios}] [-SuspendBitLocker {Never | Always}] [-UseNewSoftwareCenter <Boolean>] [-UseOnPremisesHealthAttestation <Boolean>] [-WebsitePointServerName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingComputerAgent [-AddPortalToTrustedSiteList <Boolean>] [-AllowPortalToHaveElevatedTrust <Boolean>] [-BrandingTitle <String>] [-DisableDeadlineRandom <Boolean>] [-DisableWildcardHandling] [-DisplayNewProgramNotification <Boolean>] [-EnableHealthAttestation <Boolean>] [-EnableThirdPartyOrchestration {No | Yes}] [-FinalReminderMins <Int32>] [-ForceWildcardHandling] [-HealthAttestationUrl <String>] [-InitialReminderHr <Int32>] -InputObject <IResultObject> [-InstallRestriction {AllUsers | OnlyAdministrators | OnlyAdministratorsAndPrimaryUsers | NoUsers}] [-InterimReminderHr <Int32>] [-PassThru] [-PortalUrl <String>] [-PowerShellExecutionPolicy {AllSigned | Bypass | Restricted}] [-SelectWebsitePoint {Fqdn | AutoDetect | NetBios}] [-SuspendBitLocker {Never | Always}] [-UseNewSoftwareCenter <Boolean>] [-UseOnPremisesHealthAttestation <Boolean>] [-WebsitePointServerName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingComputerAgent [-AddPortalToTrustedSiteList <Boolean>] [-AllowPortalToHaveElevatedTrust <Boolean>] [-BrandingTitle <String>] [-DisableDeadlineRandom <Boolean>] [-DisableWildcardHandling] [-DisplayNewProgramNotification <Boolean>] [-EnableHealthAttestation <Boolean>] [-EnableThirdPartyOrchestration {No | Yes}] [-FinalReminderMins <Int32>] [-ForceWildcardHandling] [-HealthAttestationUrl <String>] [-InitialReminderHr <Int32>] [-InstallRestriction {AllUsers | OnlyAdministrators | OnlyAdministratorsAndPrimaryUsers | NoUsers}] [-InterimReminderHr <Int32>] -Name <String> [-PassThru] [-PortalUrl <String>] [-PowerShellExecutionPolicy {AllSigned | Bypass | Restricted}] [-SelectWebsitePoint {Fqdn | AutoDetect | NetBios}] [-SuspendBitLocker {Never | Always}] [-UseNewSoftwareCenter <Boolean>] [-UseOnPremisesHealthAttestation <Boolean>] [-WebsitePointServerName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
