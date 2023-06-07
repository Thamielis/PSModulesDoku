Remove-CMSecondarySite
----------------------




### Synopsis
Removes a secondary site from Configuration Manager.



---


### Description

The Remove-CMSecondarySite cmdlet removes a secondary site from Configuration Manager. A secondary site has no site database of its own. Instead it is connected to a primary site and sends client data to the primary site for storage.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Invoke-CMSecondarySiteUpgrade](Invoke-CMSecondarySiteUpgrade)



* [New-CMSecondarySite](New-CMSecondarySite)





---


### Examples
#### Example 1: Remove a secondary site upgrade by using a site name
```PowerShell
PS XYZ:\> Remove-CMSecondarySite -Action Delete -SiteName "ClientSecSiteUpgrade03"
```
This command deletes a secondary site named ClientSecSiteUpgrade03. Because the Force parameter is not specified, you must confirm the action before it is performed.


---


### Parameters
#### **Action**

Specifies an action type for the deletion. The acceptable values for this parameter are:


* Delete. Removes the reference to the secondary site from the database. - Uninstall. Removes the reference to the secondary site from the database and triggers an uninstall action at the secondary site server.



Valid Values:

* Uninstall
* Delete






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[ActionType]`|true    |named   |False        |



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

Specifies a secondary site object. To obtain this object, use the New-CMSecondarySite cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies the name of a secondary site.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteName|



#### **SiteCode**

Specifies a code for a secondary site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMSecondarySite -Action {Uninstall | Delete} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecondarySite -Action {Uninstall | Delete} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecondarySite -Action {Uninstall | Delete} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
