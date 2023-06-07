Invoke-CMSecondarySiteUpgrade
-----------------------------




### Synopsis
Invokes a secondary site upgrade.



---


### Description

The Invoke-CMSecondarySiteUpgrade cmdlet invokes a secondary site upgrade that is outside of any scheduled upgrades. You can specify the site upgrade by using its name or ID, or by specifying an object that represents the site upgrade.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMSecondarySite](New-CMSecondarySite)



* [Remove-CMSecondarySite](Remove-CMSecondarySite)





---


### Examples
#### Example 1: Invoke a secondary site upgrade by using a site name
```PowerShell
PS XYZ:\>Invoke-CMSecondarySiteUpgrade -SiteName "ClientSecSiteUpgrade03" -Force
```
This command invokes a secondary site upgrade from a site named ClientSecSiteUpgrade03. Because the Force parameter is specified, Configuration Manager invokes the update automatically and does not prompt you for confirmation.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a secondary site upgrade object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SecondarySiteCode**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteCode|



#### **SecondarySiteName**








|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



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
* 






---


### Notes




---


### Syntax
```PowerShell
Invoke-CMSecondarySiteUpgrade [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMSecondarySiteUpgrade [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecondarySiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMSecondarySiteUpgrade [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecondarySiteName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
