Get-CMDiscoveryMethod
---------------------




### Synopsis
Gets a discovery method for Configuration Manager.



---


### Description

The Get-CMDiscoveryMethod cmdlet gets a discovery method for Configuration Manager. Discovery identifies computer and user resources that Configuration Manager can manage. If it discovers a resource, Configuration Manager creates a record in the Configuration Manager database for the resource and its associated information. You can then use the discovery information to help you to install the Configuration Manager client and create custom queries and collections to logically group resources for related management tasks.



For more information about discovery in Configuration Manager, see About Configuration Manager Discovery (/mem/configmgr/core/servers/deploy/configure/run-discovery).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [About Configuration Manager Discovery](About Configuration Manager Discovery)



* [Set-CMDiscoveryMethod](Set-CMDiscoveryMethod)





---


### Examples
#### Example 1: Get a user discovery method
```PowerShell
PS XYZ:\> Get-CMDiscoveryMethod -Name "ActiveDirectoryUserDiscovery"
```
This command gets a Configuration Manager method that discovers users in the installation.


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



#### **Name**

Specifies the type of discovery method that the cmdlet gets. The acceptable values for this parameter are:


* ActiveDirectoryForestDiscovery: Discovers security groups, including local, global, and universal groups from specified locations in Active Directory Domain Services.


* ActiveDirectoryGroupDiscovery: Discovers additional information, including the OU and group membership of the computer, about previously discovered computers from specified locations in Active Directory Domain Services.


* ActiveDirectorySystemDiscovery: Discovers computers from specified locations in Active Directory Domain Services.


* ActiveDirectoryUserDiscovery: Discovers users from specified locations in Active Directory Domain Services.


* HeartbeatDiscovery: Updates discovery records for Configuration Manager clients in the Configuration Manager database without discovering new resources.


* NetworkForestDiscovery: Searches the network infrastructure for network devices (such as printers, routers, and bridges) that have an IP address.



Valid Values:

* ActiveDirectoryForestDiscovery
* ActiveDirectoryGroupDiscovery
* ActiveDirectorySystemDiscovery
* ActiveDirectoryUserDiscovery
* NetworkDiscovery
* HeartbeatDiscovery






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[DiscoveryType]`|false   |named   |False        |



#### **SiteCode**

Specifies a site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_Component


* IResultObject#SMS_SCI_Component


* IResultObject[]#SMS_SCI_ClientConfig


* IResultObject#SMS_SCI_ClientConfig






---


### Notes




---


### Syntax
```PowerShell
Get-CMDiscoveryMethod [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name {ActiveDirectoryForestDiscovery | ActiveDirectoryGroupDiscovery | ActiveDirectorySystemDiscovery | ActiveDirectoryUserDiscovery | NetworkDiscovery | HeartbeatDiscovery}] [-SiteCode <String>] [<CommonParameters>]
```
