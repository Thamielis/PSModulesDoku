Get-CMSiteRole
--------------




### Synopsis
Get a site role object.



---


### Description

Returns the roles installed on a Configuration Manager site system server. For example, a management point or distribution point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMSiteRole](Remove-CMSiteRole)



* [Get-CMSiteFeature](Get-CMSiteFeature)



* [Get-CMSiteSystemServer](Get-CMSiteSystemServer)





---


### Examples
#### Example 1: Get all roles from all sites
```PowerShell
Get-CMSiteRole -AllSite
```

#### Example 2: Get all roles for a specific site
```PowerShell
Get-CMSiteRole -SiteCode P01
```

#### Example 3: Get roles for a specific server
```PowerShell
Get-CMSiteRole -SiteSystemServerName "cm01.contoso.local"
```

#### Example 4: Count all management points
```PowerShell
$mp = Get-CMSiteRole -RoleName "SMS Management Point" -AllSite
$mp.Count
```

#### Example 5: List all roles by name
```PowerShell
$allRoles = Get-CMSiteRole -AllSite
$allRoles.RoleName
```



---


### Parameters
#### **AllSite**

Include this parameter to get all of the roles for the site.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[Switch]`|false   |named   |False        |AllSites|



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








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **RoleName**

Specify a specific role name to get. The value is the string from the RoleName property on the SMS_SCI_SysResUse class. For example:


* `SMS Site System`


* `SMS Component Server`


* `SMS Distribution Point`


* `SMS Management Point`


* `SMS Device Management Point`


* `SMS Software Update Point`


* `SMS Enrollment Server`


* `SMS Enrollment Web Site`


* `SMS Notification Server`


* `SMS Certificate Registration Point`


* `SMS DM Enrollment Service`


* `SMS Site Server`


* `SMS State Migration Point`


* `SMS Provider`


* `SMS Cloud Proxy Connector`


* `SMS SQL Server`


* `SMS Fallback Status Point`


* `AI Update Service Point`


* `SMS SRS Reporting Point`


* `SMS Endpoint Protection Point`


* `Data Warehouse Service Point`


* `SMS Dmp Connector`




> [!NOTE] > This list may not include all possible site roles.







|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteCode**

Specify the site code for the specific site role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the name of a specific site system server from which to get the role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|false   |0       |False        |Name<br/>ServerName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_SCI_SysResUse


* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Get-CMSiteRole [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMSiteRole [[-SiteSystemServerName] <String>] [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] [-RoleName <String>] [-SiteCode <String>] [<CommonParameters>]
```
