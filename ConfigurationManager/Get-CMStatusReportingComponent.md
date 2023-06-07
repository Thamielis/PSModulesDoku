Get-CMStatusReportingComponent
------------------------------




### Synopsis
Gets an object representing a status reporting component.



---


### Description

The Get-CMStatusReportingComponent cmdlet gets an object that represents the status reporting component. This object provides information about the client configuration and server configuration components.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMStatusReportingComponent](Set-CMStatusReportingComponent)





---


### Examples
#### Example 1: Get status reporting components
```PowerShell
PS XYZ:\> Get-CMStatusReportingComponent -SiteCode "CM1"
```
This command gets the status reporting components that Set-CMStatusReportingComponent configures for the site.


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

Specifies a site code of a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies an array of site system server names.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_ClientConfig


* IResultObject#SMS_SCI_ClientConfig


* IResultObject[]#SMS_SCI_Configuration


* IResultObject#SMS_SCI_Configuration






---


### Notes




---


### Syntax
```PowerShell
Get-CMStatusReportingComponent [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-SiteSystemServerName <String>] [<CommonParameters>]
```
