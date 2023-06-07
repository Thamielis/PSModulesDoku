Set-CMSoftwareUpdateBasedClientInstallation
-------------------------------------------




### Synopsis
Modifies a client installation on a Configuration Manager software update point.



---


### Description

The Set-CMSoftwareUpdateBasedClientInstallation cmdlet modifies a client installation hosted on a software update point for Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateBasedClientInstallation](Get-CMSoftwareUpdateBasedClientInstallation)





---


### Examples
#### Example 1: Modify a client installation to enable WSUS
```PowerShell
PS XYZ:\> Set-CMSoftwareUpdateBasedClientInstallation -EnableWSUS $True -SiteCode "CM1"
```
This command enables WSUS for a client installation.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableWsus**

Indicates whether to enable Windows Server Update Service (WSUS).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specifies a name in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteName|



#### **SiteCode**

Specifies the Configuration Manager site for which the client installation method is configured.






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
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMSoftwareUpdateBasedClientInstallation [-DisableWildcardHandling] -EnableWsus <Boolean> [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdateBasedClientInstallation [-DisableWildcardHandling] -EnableWsus <Boolean> [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
