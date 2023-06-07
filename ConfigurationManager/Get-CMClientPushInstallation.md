Get-CMClientPushInstallation
----------------------------




### Synopsis
Gets an object that installs a Configuration Manager client by using client push.



---


### Description

The Get-CMClientPushInstallation cmdlet gets an object that installs a Configuration Manager client by using client push. A client push installation installs client software on computers that Configuration Manager discovered. When you configure client push installation for a site, the client installation automatically runs on the computers that Configuration Manager discovered within the site's configured boundaries when those boundaries are part of a boundary group. You can also start a client push installation by running the Client Push Installation Wizard for a specific collection or resource within a collection.



For more information about how to install clients, see How to Install Clients on Windows Computers in Configuration Manager (/mem/configmgr/core/clients/deploy/deploy-clients-to-windows-computers).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [How to Install Clients on Windows Computers in Configuration Manager](How to Install Clients on Windows Computers in Configuration Manager)



* [Set-CMClientPushInstallation](Set-CMClientPushInstallation)





---


### Examples
#### Example 1: Get a client push installation
```PowerShell
PS XYZ:\> Get-CMClientPushInstallation -SiteSystemServerName "CMClientPushInstallationPoint.Western.Contoso.com"
```
This command gets the client push installation for the site system server named CMClientPushInstallationPoint.Western.Contoso.com.


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

Specifies an array of site codes that identify sites on which Configuration Manager installs the client.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies an array of names of site system servers. Site system servers contain roles that define the operations that each site can perform.






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
Get-CMClientPushInstallation [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-SiteSystemServerName <String>] [<CommonParameters>]
```
