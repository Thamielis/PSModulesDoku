Add-CMEnrollmentPoint
---------------------




### Synopsis
Adds an enrollment point to Configuration Manager.



---


### Description

The Add-CMEnrollmentPoint cmdlet adds an enrollment point to a Configuration Manager site. An enrollment point is a site system role that manages enrollment requests from mobile devices.



When Configuration Manager enrolls a mobile device, it installs a Configuration Manager client. The client provides management capabilities that include hardware inventory, software deployment, settings, and remote wipe. To enroll mobile devices, use Microsoft Certificate Services with an enterprise certification authority. You need a Configuration Manager enrollment point site system role, as well as an enrollment proxy point site system role. For more information about site system roles, see Install and Configure Site System Roles for Configuration Manager (/mem/configmgr/core/servers/deploy/configure/install-site-system-roles).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMEnrollmentProxyPoint](Add-CMEnrollmentProxyPoint)



* [Get-CMEnrollmentPoint](Get-CMEnrollmentPoint)



* [Remove-CMEnrollmentPoint](Remove-CMEnrollmentPoint)





---


### Examples
#### Example 1: Add an enrollment point
```PowerShell
PS XYZ:\>Add-CMEnrollmentPoint -SiteCode "CM4" -SiteSystemServerName "Server04.Building02.Contoso.com" -IISWebsite "Intranet17" -PortNumber 80 -UserName "QADept\Admins" -WebApplicationName "Tracker"
```
This command adds an enrollment point for the site that has the site code CM4 to the server named Server04.Building02.Contoso.com. The command specifies an IIS website and port number, and the user name that the enrollment point uses to connect to the Configuration Manager database. This command also specifies the web application name.


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

Specifies the port to use with an enrollment point.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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



#### **UserName**

Specifies an account that the enrollment point uses to connect to the Configuration Manager database.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **WebApplicationName**

Specifies the name of the web application used for enrollment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Add-CMEnrollmentPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PortNumber <Int32>] [-WebApplicationName <String>] [-WebsiteName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMEnrollmentPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PortNumber <Int32>] [-SiteCode <String>] [-UserName <String>] [-WebApplicationName <String>] [-WebsiteName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
