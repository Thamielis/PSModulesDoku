Get-CMSite
----------




### Synopsis
Gets one or more Configuration Manager sites.



---


### Description

The Get-CMSite cmdlet gets one or more Configuration Manager sites. A Configuration Manager site is a server that has clients assigned to it and that processes client-generated data. You can get a Configuration Manager site by using either a site name or a site code.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMSite](Set-CMSite)





---


### Examples
#### Example 1: Get a site by using a site name
```PowerShell
PS XYZ:\> Get-CMSite -SiteName "CMSiteSystem"
```
This command gets a Configuration Manager site by using the site name CMSiteSystem.


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



#### **Name**

Specifies the name of a Configuration Manager site.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |SiteName|



#### **SiteCode**

Specifies a site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |0       |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_Site


* IResultObject#SMS_Site






---


### Notes




---


### Syntax
```PowerShell
Get-CMSite [[-SiteCode] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
