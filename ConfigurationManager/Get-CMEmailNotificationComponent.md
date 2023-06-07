Get-CMEmailNotificationComponent
--------------------------------




### Synopsis
Gets an email notification components.



---


### Description

The Get-CMEmailNotificationComponent cmdlet gets one or more email notification components Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMEmailNotificationComponent](Set-CMEmailNotificationComponent)





---


### Examples
#### Example 1: Get an email notification component by using a site code
```PowerShell
PS XYZ:\> Get-CMEmailNotificationComponent -SiteCode "CM2"
```
This command gets a notification component for the site that has the site code CM2.
#### Example 2: Get an email notification component by using a site system server name
```PowerShell
PS XYZ:\> Get-CMEmailNotificationComponent -SiteSystemServerName "CMCEN-DIST02.TSQA.CORP.CONTOSCO.COM"
```
This command gets a notification component for the site that has the server that has the specified name.


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

Specifies the three-letter site code of the Configuration Manager site that hosts the site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies an array of fully qualified domain names (FQDN) of the servers that host the site system role.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Name   |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_Component


* IResultObject#SMS_SCI_Component






---


### Notes




---


### Syntax
```PowerShell
Get-CMEmailNotificationComponent [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-SiteSystemServerName <String>] [<CommonParameters>]
```
