Get-CMFallbackStatusPoint
-------------------------




### Synopsis
Gets a Configuration Manager fallback status point.



---


### Description

The Get-CMFallbackStatusPoint cmdlet gets a fallback status point site server role. You can get fallback status point for a site system name or a site code or both.



Configuration Manager can use one or more fallback status points to collect state messages for a site and send them on to Configuration Manager. You can use this cmdlet to get a fallback status point to use with other cmdlets, such as the Set-CMFallbackStatusPoint cmdlet or the Remove-CMFallbackStatusPoint cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMFallbackStatusPoint](Add-CMFallbackStatusPoint)



* [Remove-CMFallbackStatusPoint](Remove-CMFallbackStatusPoint)



* [Set-CMFallbackStatusPoint](Set-CMFallbackStatusPoint)





---


### Examples
#### Example 1: Get a fallback status point
```PowerShell
PS XYZ:\> Get-CMFallbackStatusPoint -SiteCode "CM1" -SiteSystemServerName "Server21.West01.Contoso.com"
```
This command gets a fallback status point for the site with the site code cm1 and the system name Server21.West01.Contoso.com. You can have more than one fallback status point for a site. This example specifies both the site code and the server name.


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

Specifies the site code for a fallback status point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the site system name for a fallback status point.






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
Get-CMFallbackStatusPoint [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMFallbackStatusPoint [[-SiteSystemServerName] <String>] [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
