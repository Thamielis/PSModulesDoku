Get-CMSiteInstallStatus
-----------------------




### Synopsis
Provides information about Configuration Manager installation status.



---


### Description

The Get-CMSiteInstallStatus cmdlet provides information about the installation status for Configuration Manager. You can specify an installation by ID or by site code.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Get site installation status
```PowerShell
PS XYZ:\> Get-CMSiteInstallStatus -SiteCode "CM1"
```
This command gets the site installation status for the site that has the specified site code.


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



#### **Id**

Specifies an array of IDs for Configuration Manager installations.






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[String]`|true    |named   |False        |SiteInstallId|



#### **SiteCode**

Specifies a site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SecondarySiteStatus


* IResultObject#SMS_SecondarySiteStatus






---


### Notes




---


### Syntax
```PowerShell
Get-CMSiteInstallStatus [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMSiteInstallStatus [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
