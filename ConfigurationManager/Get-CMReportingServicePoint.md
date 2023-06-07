Get-CMReportingServicePoint
---------------------------




### Synopsis
Get a reporting service point.



---


### Description

Use this cmdlet to get a reporting service point site system role. A reporting service point is a site system role that's installed on a server that runs Microsoft SQL Server Reporting Services. For more information, see Introduction to reporting in Configuration Manager (/mem/configmgr/core/servers/manage/introduction-to-reporting).



> [!IMPORTANT] > This cmdlet doesn't support PowerShell 7 (/powershell/sccm/overview#support-for-powershell-version-7).<!-- 12500019 --> It requires the .NET Framework instead of .NET Core that's used with PowerShell version 7.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMReportingServicePoint](Add-CMReportingServicePoint)



* [Remove-CMReportingServicePoint](Remove-CMReportingServicePoint)



* [Set-CMReportingServicePoint](Set-CMReportingServicePoint)





---


### Examples
#### Example 1: Get a reporting service point
```PowerShell
Get-CMReportingServicePoint -SiteSystemServerName "CMCEN-DIST02.TSQA.CORP.CONTOSCO.COM" -SiteCode "CM1"
```



---


### Parameters
#### **AllSite**

Add this parameter to get the reporting service points from all sites in the hierarchy.






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

Specify a site system server object that has the reporting service point role. To get this object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SiteCode**

Specify the three-character code for the site that manages the system role for the reporting service point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the name of the site system server that hosts the reporting service point role.






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
For more information on this return object and its properties, see SMS_SCI_SysResUse server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_sci_sysresuse-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMReportingServicePoint [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMReportingServicePoint [[-SiteSystemServerName] <String>] [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
