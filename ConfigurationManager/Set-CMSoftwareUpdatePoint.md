Set-CMSoftwareUpdatePoint
-------------------------




### Synopsis
Configure a software update point.



---


### Description

Use this cmdlet to change settings for a software update point site system role.



Configure the settings that a software update point uses when connecting with clients and with a WSUS server. To configure the site component for software update point, use the Set-CMSoftwareUpdatePointComponent (Set-CMSoftwareUpdatePointComponent.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMSoftwareUpdatePoint](Add-CMSoftwareUpdatePoint)



* [Get-CMSoftwareUpdatePoint](Get-CMSoftwareUpdatePoint)



* [Remove-CMSoftwareUpdatePoint](Remove-CMSoftwareUpdatePoint)



* [Set-CMSoftwareUpdatePointComponent](Set-CMSoftwareUpdatePointComponent)





---


### Examples
#### Example 1: Modify the ports
```PowerShell
Set-CMSoftwareUpdatePoint -SiteCode "CM1" -SiteSystemServerName "CMSoftwareUpdatePoint.TSQA.Contoso.com" -HttpPort 8530 -HttpsPort 8531
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



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableCloudGateway**

Add this parameter to allow cloud management gateway (CMG) traffic to this software update point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSsl**

Set this parameter to `$true` to require SSL communication to the WSUS server.


For more information, see Configure a software update point to use TLS/SSL with a PKI certificate (/mem/configmgr/sum/get-started/software-update-point-ssl).






|Type       |Required|Position|PipelineInput|Aliases            |
|-----------|--------|--------|-------------|-------------------|
|`[Boolean]`|false   |named   |False        |SslWsus<br/>WsusSsl|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **HttpPort**

Specify an integer value for the HTTP port to use for the WSUS server. By default, this value is `8530`.






|Type     |Required|Position|PipelineInput|Aliases    |
|---------|--------|--------|-------------|-----------|
|`[Int32]`|false   |named   |False        |WsusIisPort|



#### **HttpsPort**

Specify an integer value for the HTTPS port to use for the WSUS server. By default, this value is `8531`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|false   |named   |False        |WsusIisSslPort|



#### **InputObject**

Specify a site system server object on which to configure the software update point role. To get this object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SoftwareUpdatePoint|



#### **NlbVirtualIP**

Failover support for a software update point in a network load balancing (NLB) cluster was deprecated in version 1702. For more information, see Removed and deprecated features (/mem/configmgr/core/plan-design/changes/deprecated/removed-and-deprecated-cmfeatures#unsupported-and-removed-features).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PublicVirtualIP**

Specify a public virtual IP address for a software update point that's connected to the internet.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteCode**

Specify the three-character code for the site that manages the system role for the software update point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the name of the site system server that hosts the software update point role.






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



#### **WsusAccessAccount**

Specify the user name for the WSUS server connection account. This account provides authenticated access from the site to the WSUS server. For more information, see Accounts used in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/accounts#software-update-point-connection-account).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Set-CMSoftwareUpdatePoint [-AnonymousWsusAccess] [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-DisableWildcardHandling] [-EnableCloudGateway <Boolean>] [-EnableSsl <Boolean>] [-ForceWildcardHandling] [-HttpPort <Int32>] [-HttpsPort <Int32>] -InputObject <IResultObject> [-NlbVirtualIP <String>] [-PassThru] [-PublicVirtualIP <String>] [-UseProxy <Boolean>] [-UseProxyForAutoDeploymentRule <Boolean>] [-WsusAccessAccount <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdatePoint [-SiteSystemServerName] <String> [-AnonymousWsusAccess] [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-DisableWildcardHandling] [-EnableCloudGateway <Boolean>] [-EnableSsl <Boolean>] [-ForceWildcardHandling] [-HttpPort <Int32>] [-HttpsPort <Int32>] [-NlbVirtualIP <String>] [-PassThru] [-PublicVirtualIP <String>] [-SiteCode <String>] [-UseProxy <Boolean>] [-UseProxyForAutoDeploymentRule <Boolean>] [-WsusAccessAccount <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
