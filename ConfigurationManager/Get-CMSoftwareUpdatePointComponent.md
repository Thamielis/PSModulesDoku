Get-CMSoftwareUpdatePointComponent
----------------------------------




### Synopsis
Get the site component for the software update point.



---


### Description

Use this cmdlet to get the site component for the software update point. You can use the cmdlet to view the component configuration, or to get an object to configure with the Set-CMSoftwareUpdatePointComponent (Set-CMSoftwareUpdatePointComponent.md)cmdlet.



A software update point component interacts with a Windows Server Update Services (WSUS) server to configure update settings, request synchronization to the upstream update source, and synchronize updates from the WSUS database to the site server database on the central site.



For more information, see Site components for Configuration Manager (/mem/configmgr/core/servers/deploy/configure/site-components).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMSoftwareUpdatePointComponent](Set-CMSoftwareUpdatePointComponent)



* [Site components for Configuration Manager](Site components for Configuration Manager)





---


### Examples
#### Example 1: Get a software update point component by name
```PowerShell
Get-CMSoftwareUpdatePointComponent -SiteSystemServerName "Contoso-SiteSysSrv.Western.Contoso.com"
```

#### Example 2: Get a software update point component by site code
```PowerShell
Get-CMSoftwareUpdatePointComponent -SiteCode "CM1"
```

#### Example 3: Show the status of third-party updates in the hierarchy
```PowerShell
$SUPWsusSyncMgr = Get-CMSoftwareUpdatePointComponent -WsusSyncManager

$SUPWsusSyncMgr.Props | Where PropertyName -eq "EnableThirdPartyUpdates"
```



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

Specify the three-character code for the site from which to get the software update point component.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the FQDN of a site system server that has the software update point role.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Name   |



#### **WsusSyncManager**

By default, this cmdlet gets objects and properties from the SMS_WSUS_CONFIGURATION_MANAGER component. Add this parameter to get objects and properties from the SMS_WSUS_SYNC_MANAGER component.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_Component


* IResultObject#SMS_SCI_Component






---


### Notes
For more information on this return object and its properties, see SMS_SCI_Component server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_sci_component-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMSoftwareUpdatePointComponent [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-SiteSystemServerName <String>] [-WsusSyncManager] [<CommonParameters>]
```
