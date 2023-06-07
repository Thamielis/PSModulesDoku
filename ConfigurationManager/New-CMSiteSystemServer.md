New-CMSiteSystemServer
----------------------




### Synopsis
Add a new site system server.



---


### Description

Use this cmdlet to create a new site system server. A server with the Site system role hosts one or more other roles for a Configuration Manager site.



To add specific site system roles, use one of the following cmdlets:



- Add-CMAssetIntelligenceSynchronizationPoint (Add-CMAssetIntelligenceSynchronizationPoint.md)- Add-CMCertificateRegistrationPoint (Add-CMCertificateRegistrationPoint.md)- Add-CMCloudManagementGatewayConnectionPoint (Add-CMCloudManagementGatewayConnectionPoint.md)- Add-CMDataWarehouseServicePoint (Add-CMDataWarehouseServicePoint.md)- Add-CMDistributionPoint (Add-CMDistributionPoint.md)- Add-CMEndpointProtectionPoint (Add-CMEndpointProtectionPoint.md)- Add-CMFallbackStatusPoint (Add-CMFallbackStatusPoint.md)- Add-CMManagementPoint (Add-CMManagementPoint.md)- Add-CMMulticastServicePoint (Add-CMMulticastServicePoint.md)- Add-CMReportingServicePoint (Add-CMReportingServicePoint.md)- Add-CMServiceConnectionPoint (Add-CMServiceConnectionPoint.md)- Add-CMSoftwareUpdatePoint (Add-CMSoftwareUpdatePoint.md)- Add-CMStateMigrationPoint (Add-CMStateMigrationPoint.md)> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSiteSystemServer](Get-CMSiteSystemServer)



* [Remove-CMSiteSystemServer](Remove-CMSiteSystemServer)



* [Set-CMSiteSystemServer](Set-CMSiteSystemServer)





---


### Examples
#### Example 1: Create a site system server
```PowerShell
New-CMSiteSystemServer -SiteSystemServerName "Server1.contoso.com" -SiteCode "MP5" -PublicFqdn "Internetsrv1.contoso.com" -FdmOperation $True -UseSiteServerAccount -EnableProxy $True -ProxyServerName "ProxyServer1" -ProxyServerPort 80 -ProxyAccessAccount (Get-CMAccount "contoso\proxysvc")
```



---


### Parameters
#### **AccountName**

Specify the account for installing this site system, and the account used for all connections from the site server. For more information, see Site system installation account (/mem/configmgr/core/plan-design/hierarchy/accounts#site-system-installation-account).


To use the site server's computer account, use the UseSiteServerAccount parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableProxy**

Set this parameter to `$true` for the site system to use a proxy server when it synchronizes information from the internet.


If you enable this option, also configure the following parameters:


* ProxyServerName


* ProxyServerPort


* ProxyAccessAccount






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **FdmOperation**

Set this parameter to `$true` to require the site server to initiate connections to this site system.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ProxyAccessAccount**

If you set EnableProxy to `$true`, use this parameter to specify an account object. The site system uses these credentials to authenticate to the proxy server. To get this account object, use the Get-CMAccount (Get-CMAccount.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **ProxyServerName**

If you set EnableProxy to `$true`, use this parameter to specify the name of the proxy server. This parameter accepts the following types of values:


* Fully qualified domain name (FQDN)


* Hostname


* IPv4 or IPv6 address






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ProxyServerPort**

If you set EnableProxy to `$true`, use this parameter to specify the proxy server port number.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|false   |named   |False        |



#### **PublicFqdn**

Specify an FQDN for the site system to use on the internet.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteCode**

Specify the site code for this site system.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the name of the site system server to configure.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |ServerName<br/>Name|



#### **UseSiteServerAccount**

Add this parameter to use the site server's computer account to install this site system. For more information, see Site system installation account (/mem/configmgr/core/plan-design/hierarchy/accounts#site-system-installation-account).


To use another account, use the UseSiteServerAccount parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
New-CMSiteSystemServer [-SiteSystemServerName] <String> [-AccountName <String>] [-DisableWildcardHandling] [-EnableProxy <Boolean>] [-FdmOperation <Boolean>] [-ForceWildcardHandling] [-ProxyAccessAccount <IResultObject>] [-ProxyServerName <String>] [-ProxyServerPort <UInt32>] [-PublicFqdn <String>] [-SiteCode <String>] [-UseSiteServerAccount] [-Confirm] [-WhatIf] [<CommonParameters>]
```
