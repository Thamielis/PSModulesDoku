Get-CMSoftwareUpdateBasedClientInstallation
-------------------------------------------




### Synopsis
Gets a client installation on a Configuration Manager software update point.



---


### Description

The Get-CMSoftwareUpdateBasedClientInstallation cmdlet gets a client installation hosted on a software update point for Configuration Manager.



Configuration Manager publishes the Configuration Manager client to a software update point. This site system role can install the client on computers that do not already have it or upgrade existing clients.



To use software update point based installation, you must use the same Windows Server Update Services (WSUS) server for both client installation and software updates. This server must be the active software update point in a primary site.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMSoftwareUpdateBasedClientInstallation](Set-CMSoftwareUpdateBasedClientInstallation)





---


### Examples
#### Example 1: Get a client installation
```PowerShell
PS XYZ:\> Get-CMSoftwareUpdateBasedClientInstallation -SiteCode "CM1"
```
This command gets the client installation for the site that has the site code CM1.


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



#### **SiteCode**

Specifies a site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies an array of names of servers that host a software update point role.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Name   |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_Component


* IResultObject#SMS_SCI_Component






---


### Notes




---


### Syntax
```PowerShell
Get-CMSoftwareUpdateBasedClientInstallation [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-SiteSystemServerName <String>] [<CommonParameters>]
```
