Get-CMIPSubnet
--------------




### Synopsis
Gets a Configuration Manager IP subnet.



---


### Description

The Get-CMIPSubnet cmdlet gets an IP subnet object that Configuration Manager uses as a boundary.



A boundary is a network location on the intranet that can contain one or more devices that you want to manage. Configuration Manager can define a boundary in several ways, including an IP subnet. For more information about boundaries, see Planning for Boundaries and Boundary Groups in Configuration Manager (/mem/configmgr/core/servers/deploy/configure/define-site-boundaries-and-boundary-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMActiveDirectorySite](Get-CMActiveDirectorySite)





---


### Examples
#### Example 1: Get an IP subnet
```PowerShell
PS XYZ:\> Get-CMIPSubnet -Name "West07Subnet"
```
This command gets the IP subnet object named West07Subnet.


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



#### **Id**

Specifies an array of IDs for IP subnets. This is a Configuration Manager name, not an IP address or IP address and subnet.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SubnetId|



#### **Name**

Specifies an array of names for IP subnets.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |ADSubnetName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_ADSubnet


* IResultObject#SMS_ADSubnet






---


### Notes




---


### Syntax
```PowerShell
Get-CMIPSubnet [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMIPSubnet [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
