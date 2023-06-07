New-CMBoundary
--------------




### Synopsis
Create a site boundary.



---


### Description

Use this cmdlet to create a site boundary. A boundary is a network location that contains one or more devices that you can manage. A boundary can be an IP subnet, Active Directory site name, IPv6 prefix, an IP address range, or a VPN. For more information, see Define site boundaries and boundary groups (/mem/configmgr/core/servers/deploy/configure/define-site-boundaries-and-boundary-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBoundary](Get-CMBoundary)



* [Remove-CMBoundary](Remove-CMBoundary)



* [Set-CMBoundary](Set-CMBoundary)





---


### Examples
#### Example 1: Create an IP subnet site boundary
```PowerShell
New-CMBoundary -DisplayName "IPSubNetBoundary01" -BoundaryType IPSubNet -Value "172.16.50.0/24"
```

#### Example 2: Create an Active Directory site boundary
```PowerShell
New-CMBoundary -DisplayName "ADSiteBoundary01" -BoundaryType ADSite -Value "Default-First-Site-Name"
```

#### Example 3: Create an IPv6 prefix site boundary
```PowerShell
New-CMBoundary -DisplayName "IPv6PrefixBoundary01" -BoundaryType IPv6Prefix -Value "FE80::/64"
```

#### Example 4: Create an IP range site boundary
```PowerShell
New-CMBoundary -DisplayName "IPRangeBoundary01" -BoundaryType IPRange -Value "10.255.255.0-10.255.255.255"
```

#### Example 5: Create a VPN site boundary
```PowerShell
New-CMBoundary -DisplayName "VPN-CONTOSO1-Name" -BoundaryType VPN -Value "Name:CONTOSO1"
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



#### **Name**

Specify the name of the new boundary.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |DisplayName|



#### **Type**

Specify the boundary type.



Valid Values:

* IPSubnet
* ADSite
* IPV6Prefix
* IPRange
* Vpn






|Type             |Required|Position|PipelineInput|Aliases     |
|-----------------|--------|--------|-------------|------------|
|`[BoundaryTypes]`|true    |named   |False        |BoundaryType|



#### **Value**

Specify the data that defines the boundary. For example, an Active Directory site value can be `Default-First-Site-Name`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ValueStartsWith**

Set this parameter to `$true` to match the start of a connection name or description instead of the whole string. For more information, see Define network locations as boundaries (/mem/configmgr/core/servers/deploy/configure/boundaries#vpn).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
None





---


### Outputs
* IResultObject#SMS_Boundary






---


### Notes
For more information on this return object and its properties, see SMS_Boundary server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_boundary-server-wmi-class).



---


### Syntax
```PowerShell
New-CMBoundary [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] -Type {IPSubnet | ADSite | IPV6Prefix | IPRange | Vpn} -Value <String> [-ValueStartsWith <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
