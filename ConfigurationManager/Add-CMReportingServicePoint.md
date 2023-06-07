Add-CMReportingServicePoint
---------------------------




### Synopsis
Add a reporting service point.



---


### Description

Use this cmdlet to add a reporting service point to the site. A reporting service point is a site system role that's installed on a server that run Microsoft SQL Server Reporting Services.



For more information, see Introduction to reporting in Configuration Manager (/mem/configmgr/core/servers/manage/introduction-to-reporting).



> [!IMPORTANT] > This cmdlet doesn't support PowerShell 7 (/powershell/sccm/overview#support-for-powershell-version-7).<!-- 12500019 --> It requires the .NET Framework instead of .NET Core that's used with PowerShell version 7.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMReportingServicePoint](Get-CMReportingServicePoint)



* [Remove-CMReportingServicePoint](Remove-CMReportingServicePoint)



* [Set-CMReportingServicePoint](Set-CMReportingServicePoint)





---


### Examples
#### Example 1: Add a reporting service point
```PowerShell
Add-CMReportingServicePoint -SiteCode "CM1" -SiteSystemServerName "CMReportingServicePoint.TSQA.Contoso.com"
```



---


### Parameters
#### **DatabaseName**

Specify the name of the Configuration Manager database that you want to use as the data source for reports from Microsoft SQL Server Reporting Services.


To specify a database instance, use the format `ServerName\InstanceName`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DatabaseServerName**

Specify the name of the Configuration Manager database server that you want to use as the data source for reports from Microsoft SQL Server Reporting Services.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FolderName**

Specify the name of the report folder on the report server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a site system server object on which to add the reporting service point role. To get this object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteServer|



#### **ReportServerInstance**

Specify the name of an instance of Microsoft SQL Server Reporting Services.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteCode**

Specify the three-character code for the site that manages the system role for the reporting service point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the name of the site system server to host the reporting service point role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **UserName**

Specify the user name for the Reporting services point account. This account provides authenticated access from the site to Microsoft SQL Server Reporting Services. For more information, see Accounts used in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/accounts#reporting-services-point-account).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Add-CMReportingServicePoint [-SiteSystemServerName] <String> [-DatabaseName <String>] [-DatabaseServerName <String>] [-DisableWildcardHandling] [-FolderName <String>] [-Force] [-ForceWildcardHandling] [-ReportServerInstance <String>] [-SiteCode <String>] -UserName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMReportingServicePoint [-DatabaseName <String>] [-DatabaseServerName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-ReportServerInstance <String>] -UserName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
