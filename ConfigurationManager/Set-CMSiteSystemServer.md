Set-CMSiteSystemServer
----------------------




### Synopsis
Configure the site system server role.



---


### Description

Use this cmdlet to configure the site system server role. A server with the Site system role hosts one or more other roles for a Configuration Manager site.



To configure specific site system roles, use one of the following cmdlets:



- Set-CMAssetIntelligenceSynchronizationPoint (Set-CMAssetIntelligenceSynchronizationPoint.md)- Set-CMCertificateRegistrationPoint (Set-CMCertificateRegistrationPoint.md)- Set-CMCloudManagementGatewayConnectionPoint (Set-CMCloudManagementGatewayConnectionPoint.md)- Set-CMDataWarehouseServicePoint (Set-CMDataWarehouseServicePoint.md)- Set-CMDistributionPoint (Set-CMDistributionPoint.md)- Set-CMEndpointProtectionPoint (Set-CMEndpointProtectionPoint.md)- Set-CMFallbackStatusPoint (Set-CMFallbackStatusPoint.md)- Set-CMManagementPoint (Set-CMManagementPoint.md)- Set-CMMulticastServicePoint (Set-CMMulticastServicePoint.md)- Set-CMReportingServicePoint (Set-CMReportingServicePoint.md)- Set-CMServiceConnectionPoint (Set-CMServiceConnectionPoint.md)- Set-CMSoftwareUpdatePoint (Set-CMSoftwareUpdatePoint.md)- Set-CMStateMigrationPoint (Set-CMStateMigrationPoint.md)> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSiteSystemServer](Get-CMSiteSystemServer)



* [New-CMSiteSystemServer](New-CMSiteSystemServer)



* [Remove-CMSiteSystemServer](Remove-CMSiteSystemServer)





---


### Examples
#### Example 1: Modify a site system server
```PowerShell
Get-CMSiteSystemServer -Name "Server2.contoso.com" -SiteCode "MP5" | Set-CMSiteSystemServer -PublicFqdn "Internetsrv2New.contoso.com" -FdmOperation $False -AccountName "contoso\cmsvc" -EnableProxy $True -ProxyServerName "ProxyServer1" -ProxyServerPort 80 -ProxyAccessAccount (Get-CMAccount "contoso\proxysvc") -PassThru
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



#### **InputObject**

Specify a site system server object to configure. To get this object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteSystemServer|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






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
|`[String]`|true    |0       |False        |Name<br/>ServerName|



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Set-CMSiteSystemServer [-AccountName <String>] [-DisableWildcardHandling] [-EnableProxy <Boolean>] [-FdmOperation <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-ProxyAccessAccount <IResultObject>] [-ProxyServerName <String>] [-ProxyServerPort <UInt32>] [-PublicFqdn <String>] [-UseSiteServerAccount] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSiteSystemServer [-SiteSystemServerName] <String> [-AccountName <String>] [-DisableWildcardHandling] [-EnableProxy <Boolean>] [-FdmOperation <Boolean>] [-ForceWildcardHandling] [-PassThru] [-ProxyAccessAccount <IResultObject>] [-ProxyServerName <String>] [-ProxyServerPort <UInt32>] [-PublicFqdn <String>] [-SiteCode <String>] [-UseSiteServerAccount] [-Confirm] [-WhatIf] [<CommonParameters>]
```
