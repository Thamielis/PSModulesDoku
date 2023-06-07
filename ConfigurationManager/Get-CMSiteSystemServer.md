Get-CMSiteSystemServer
----------------------




### Synopsis
Get the site system server role.



---


### Description

Use this cmdlet to get the site system server role. A server with the Site system role hosts one or more other roles for a Configuration Manager site.



To get specific site system roles, use one of the following cmdlets:



- Get-CMAssetIntelligenceSynchronizationPoint (Get-CMAssetIntelligenceSynchronizationPoint.md)- Get-CMCertificateRegistrationPoint (Get-CMCertificateRegistrationPoint.md)- Get-CMCloudManagementGatewayConnectionPoint (Get-CMCloudManagementGatewayConnectionPoint.md)- Get-CMDataWarehouseServicePoint (Get-CMDataWarehouseServicePoint.md)- Get-CMDistributionPoint (Get-CMDistributionPoint.md)- Get-CMEndpointProtectionPoint (Get-CMEndpointProtectionPoint.md)- Get-CMFallbackStatusPoint (Get-CMFallbackStatusPoint.md)- Get-CMManagementPoint (Get-CMManagementPoint.md)- Get-CMMulticastServicePoint (Get-CMMulticastServicePoint.md)- Get-CMReportingServicePoint (Get-CMReportingServicePoint.md)- Get-CMServiceConnectionPoint (Get-CMServiceConnectionPoint.md)- Get-CMSoftwareUpdatePoint (Get-CMSoftwareUpdatePoint.md)- Get-CMStateMigrationPoint (Get-CMStateMigrationPoint.md)> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMSiteSystemServer](New-CMSiteSystemServer)



* [Remove-CMSiteSystemServer](Remove-CMSiteSystemServer)



* [Set-CMSiteSystemServer](Set-CMSiteSystemServer)





---


### Examples
#### Example 1: Get a site system server
```PowerShell
Get-CMSiteSystemServer -SiteSystemServerName "Server2.contoso.com" -SiteCode "MP5"
```



---


### Parameters
#### **AllSite**

Add this parameter to look for the site system server across all sites.


To specify a specific site, use the SiteCode parameter.






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

Specify a site system object SMS_SCI_SysResUse with role name `SMS Site System`.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SiteCode**

Specify a Configuration Manager site code to look for the site system server.


To look across all sites, use the AllSite parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify a server name for the site system to get.






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
Get-CMSiteSystemServer [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMSiteSystemServer [[-SiteSystemServerName] <String>] [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
