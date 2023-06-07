Get-CMManagementPointComponent
------------------------------




### Synopsis
Gets a component for a Configuration Manager management point.



---


### Description

The Get-CMManagementPointComponent cmdlet gets a component of a management point for Configuration Manager. A management point is a Configuration Manager site that provides policy and service information to clients and receives configuration data from clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMManagementPointComponent](Set-CMManagementPointComponent)



* [Get-CMManagementPoint](Get-CMManagementPoint)



* [Remove-CMManagementPoint](Remove-CMManagementPoint)





---


### Examples
#### Example 1: Get a management point component
```PowerShell
PS XYZ:\> Get-CMManagementPointComponent -SiteCode "CM1" >>\1\Get-CMManagementPointComponent_data.txt
```
This command gets a component that is associated with the site that has the code CM1. The command directs the output to the file Get-CMManagementPointComponent_data.txt.


---


### Parameters
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



#### **SiteCode**

Specifies the site code for the management point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies a fully qualified domain name (FQDN) of the server that hosts the site system role.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Name   |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_SysResUse


* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Get-CMManagementPointComponent [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-SiteSystemServerName <String>] [<CommonParameters>]
```
