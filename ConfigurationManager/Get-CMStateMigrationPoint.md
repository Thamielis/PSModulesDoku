Get-CMStateMigrationPoint
-------------------------




### Synopsis
Gets a state migration point for a Configuration Manager site.



---


### Description

The Get-CMStateMigrationPoint cmdlet gets a state migration point for a Configuration Manager site. This site system role stores user information. You can store user information while an operating system deployment proceeds and then restore user information from the state migration point.



You can use this cmdlet to get state migration point objects to use with the Remove-CMStateMigrationPoint (Remove-CMStateMigrationPoint.md)cmdlet.



Each state migration point site server can be a member of only one Configuration Manager site.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMStateMigrationPoint](Add-CMStateMigrationPoint)



* [Remove-CMStateMigrationPoint](Remove-CMStateMigrationPoint)



* [Set-CMStateMigrationPoint](Set-CMStateMigrationPoint)





---


### Examples
#### Example 1: Get a migration point
```PowerShell
PS XYZ:\> Get-CMStateMigrationPoint -SiteCode "CM1" -SiteSystemServerName "SMP01.Western.Contoso.com"
```
This command gets a state migration point that belongs to the specified site and has the specified host name.


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

Specifies a site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the host name for a state migration point.






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
Get-CMStateMigrationPoint [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMStateMigrationPoint [[-SiteSystemServerName] <String>] [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
