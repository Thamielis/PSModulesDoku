Get-CMEndpointProtectionPoint
-----------------------------




### Synopsis
Gets an Endpoint Protection point.



---


### Description

The Get-CMEndpointProtectionPoint cmdlet gets a System Center 2016 Endpoint Protection point in Configuration Manager. For more information about Endpoint Protection in Configuration Manager, see Endpoint Protection in Configuration Manager (/mem/configmgr/protect/deploy-use/endpoint-protection).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Endpoint Protection in Configuration Manager](Endpoint Protection in Configuration Manager)



* [Add-CMEndpointProtectionPoint](Add-CMEndpointProtectionPoint)



* [Remove-CMEndpointProtectionPoint](Remove-CMEndpointProtectionPoint)



* [Set-CMEndpointProtectionPoint](Set-CMEndpointProtectionPoint)





---


### Examples
#### Example 1: Get an Endpoint Protection point
```PowerShell
PS XYZ:\> Get-CMEndpointProtectionPoint -SiteCode "CM1" -SiteSystemServerName "CMServer01.Contoso.com"
```
This command gets an Endpoint Protection point.


---


### Parameters
#### **AllSite**








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

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SiteCode**

Specifies a site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the fully qualified domain name (FQDN) of the server that hosts the site system role.






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
Get-CMEndpointProtectionPoint [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMEndpointProtectionPoint [[-SiteSystemServerName] <String>] [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
