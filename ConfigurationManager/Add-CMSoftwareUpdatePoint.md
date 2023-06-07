Add-CMSoftwareUpdatePoint
-------------------------




### Synopsis
Add a software update point.



---


### Description

Use this cmdlet to add a software update point to the site. This site system role hosts the Windows Software Update Services (WSUS) processes.



After you add the role, use the Set-CMSoftwareUpdatePointComponent (Set-CMSoftwareUpdatePointComponent.md)cmdlet to configure the site component.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdatePoint](Get-CMSoftwareUpdatePoint)



* [Remove-CMSoftwareUpdatePoint](Remove-CMSoftwareUpdatePoint)



* [Set-CMSoftwareUpdatePoint](Set-CMSoftwareUpdatePoint)



* [Set-CMSoftwareUpdatePointComponent](Set-CMSoftwareUpdatePointComponent)





---


### Examples
#### Example 1: Add a software update point
```PowerShell
Add-CMSoftwareUpdatePoint -SiteCode "CM1" -SiteSystemServerName "CMSoftwareUpdatePoint.TSQA.Contoso.com"
```



---


### Parameters
#### **AnonymousWsusAccess**

Add this parameter to indicates that the software update point allows anonymous WSUS access.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClientConnectionType**

Specify the type of the client connection.



Valid Values:

* Intranet
* Internet
* InternetAndIntranet






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[ClientConnectionTypes]`|false   |named   |False        |



#### **ConnectionAccountUserName**

Specify the user name for the WSUS server connection account. This account provides authenticated access from the site to the WSUS server. For more information, see Accounts used in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/accounts#software-update-point-connection-account).






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |UserName|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableCloudGateway**

Add this parameter to allow cloud management gateway (CMG) traffic to this software update point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a site system server object on which to add the software update point role. To get this object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SiteCode**

Specify the three-character code for the site that manages the system role for the software update point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the name of the site system server to host the software update point role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **UseProxy**

Set this parameter to `$true` to use a proxy server for software updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseProxyForAutoDeploymentRule**

When you use the UseProxy parameter, set this parameter to `$true` to use a proxy server when downloading content with an automatic deployment rule (ADR).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WsusIisPort**

Specify an integer value for the HTTP port to use for the WSUS server. By default, this value is `8530`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **WsusIisSslPort**

Specify an integer value for the HTTPS port to use for the WSUS server. By default, this value is `8531`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **WsusSsl**

Set this parameter to `$true` to require SSL communication to the WSUS server.


For more information, see Configure a software update point to use TLS/SSL with a PKI certificate (/mem/configmgr/sum/get-started/software-update-point-ssl).






|Type       |Required|Position|PipelineInput|Aliases|
|-----------|--------|--------|-------------|-------|
|`[Boolean]`|false   |named   |False        |SslWsus|



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
For more information on this return object and its properties, see SMS_SCI_SysResUse server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_sci_sysresuse-server-wmi-class).



---


### Syntax
```PowerShell
Add-CMSoftwareUpdatePoint [-AnonymousWsusAccess] [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ConnectionAccountUserName <String>] [-DisableWildcardHandling] [-EnableCloudGateway] [-ForceWildcardHandling] -InputObject <IResultObject> [-UseProxy <Boolean>] [-UseProxyForAutoDeploymentRule <Boolean>] [-WsusIisPort <Int32>] [-WsusIisSslPort <Int32>] [-WsusSsl <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSoftwareUpdatePoint [-SiteSystemServerName] <String> [-AnonymousWsusAccess] [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ConnectionAccountUserName <String>] [-DisableWildcardHandling] [-EnableCloudGateway] [-ForceWildcardHandling] [-SiteCode <String>] [-UseProxy <Boolean>] [-UseProxyForAutoDeploymentRule <Boolean>] [-WsusIisPort <Int32>] [-WsusIisSslPort <Int32>] [-WsusSsl <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
