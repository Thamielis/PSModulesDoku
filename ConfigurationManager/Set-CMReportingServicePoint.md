Set-CMReportingServicePoint
---------------------------




### Synopsis
Configure a reporting service point.



---


### Description

Use this cmdlet to change settings for a reporting service point site system role.



> [!IMPORTANT] > This cmdlet doesn't support PowerShell 7 (/powershell/sccm/overview#support-for-powershell-version-7).<!-- 12500019 --> It requires the .NET Framework instead of .NET Core that's used with PowerShell version 7.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMReportingServicePoint](Add-CMReportingServicePoint)



* [Get-CMReportingServicePoint](Get-CMReportingServicePoint)



* [Remove-CMReportingServicePoint](Remove-CMReportingServicePoint)





---


### Examples
#### Example 1: Configure the reporting service point account
```PowerShell
Set-CMReportingServicePoint -SiteSystemServerName "Contoso-Test.Contoso.Com" -SiteCode "CM4" -UserName "Contoso\DavidChew"
```

#### Example 2: Configure the reporting service point database
```PowerShell
Set-CMReportingServicePoint -SiteSystemServerName "Contoso-Test.Contoso.Com" -SiteCode "CM4" -DatabaseServerName "Contoso-TestDB.Contoso.Com" -DatabaseName "CM_CM2"
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

Specify a site system server object on which to configure the reporting service point role. To get this object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases              |
|-----------------|--------|--------|--------------|---------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ReportingServicePoint|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Set-CMReportingServicePoint [-DatabaseName <String>] [-DatabaseServerName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMReportingServicePoint [-SiteSystemServerName] <String> [-DatabaseName <String>] [-DatabaseServerName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-PassThru] [-SiteCode <String>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
