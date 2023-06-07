Add-CMEnrollmentProxyPoint
--------------------------




### Synopsis
Adds an enrollment proxy point to Configuration Manager.



---


### Description

The Add-CMEnrollmentProxyPoint cmdlet adds an enrollment proxy point to a Configuration Manager site. An enrollment proxy point is a site system role.



When Configuration Manager enrolls a mobile device, it installs a Configuration Manager client. The client provides management capabilities that include hardware inventory, software deployment, settings, and remote wipe. To enroll mobile devices, use Microsoft Certificate Services with an enterprise certification authority (CA). You need a Configuration Manager enrollment proxy point site system role, as well as an enrollment point site system role. For more information about site system roles, see Install and Configure Site System Roles for Configuration Manager (/mem/configmgr/core/servers/deploy/configure/install-site-system-roles).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMEnrollmentPoint](Add-CMEnrollmentPoint)



* [Get-CMEnrollmentProxyPoint](Get-CMEnrollmentProxyPoint)



* [Remove-CMEnrollmentProxyPoint](Remove-CMEnrollmentProxyPoint)





---


### Examples
#### Example 1: Add an enrollment proxy point
```PowerShell
PS XYZ:\>Add-CMEnrollmentProxyPoint -SiteCode "CM1" -SiteSystemServerName "CMEnrollmentProxyPoint.Western.Contoso.com"
```
This command adds an enrollment proxy point for the Configuration Manager site that has the site code CM1. The specified computer hosts the role.


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

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteServer|



#### **PortNumber**

Specifies the port that client computers use to connect with an enrollment proxy point.






|Type     |Required|Position|PipelineInput|Aliases|
|---------|--------|--------|-------------|-------|
|`[Int32]`|false   |named   |False        |Port   |



#### **ServiceHost**








|Type             |Required|Position|PipelineInput|Aliases        |
|-----------------|--------|--------|-------------|---------------|
|`[IResultObject]`|false   |named   |False        |EnrollmentPoint|



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of a server that hosts a site system role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **WebsiteName**








|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |IISWebsite|



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
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Add-CMEnrollmentProxyPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PortNumber <Int32>] [-ServiceHost <IResultObject>] [-WebsiteName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMEnrollmentProxyPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PortNumber <Int32>] [-ServiceHost <IResultObject>] [-SiteCode <String>] [-WebsiteName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
