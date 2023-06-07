Set-CMBoundary
--------------




### Synopsis
Configure a site boundary.



---


### Description

Use this cmdlet to configure a site boundary. A boundary is a network location that contains one or more devices that you can manage. A boundary can be an IP subnet, Active Directory site name, IPv6 prefix, an IP address range, or a VPN. For more information, see Define site boundaries and boundary groups (/mem/configmgr/core/servers/deploy/configure/define-site-boundaries-and-boundary-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBoundary](Get-CMBoundary)



* [New-CMBoundary](New-CMBoundary)



* [Remove-CMBoundary](Remove-CMBoundary)





---


### Examples
#### Example 1: Rename a boundary
```PowerShell
Set-CMBoundary -Name "Default-ADSite" -NewName "ADSiteBoundary01"
```

#### Example 2: Modify the value of a boundary by using an InputObject
```PowerShell
$BoundaryObj = Get-CMBoundary -Id "16777217"
Set-CMBoundary -InputObject $BoundaryObj -Value "IPSubnet17"
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



#### **Id**

Specify a boundary identifier (ID) to modify. This value is an integer, for example `26`.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |BoundaryId|



#### **InputObject**

Specify a boundary object to modify. To get this object, use the Get-CMBoundary (Get-CMBoundary.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **NewName**

Specify a new name for a boundary.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |DisplayName<br/>Name|



#### **NewType**

Specify the boundary type.



Valid Values:

* IPSubnet
* ADSite
* IPV6Prefix
* IPRange
* Vpn






|Type             |Required|Position|PipelineInput|Aliases        |
|-----------------|--------|--------|-------------|---------------|
|`[BoundaryTypes]`|false   |named   |False        |NewBoundaryType|



#### **NewValue**

Specify the data that defines the boundary. For example, an Active Directory site value can be `Default-First-Site-Name`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Type**

Specify a boundary type.



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

Specify the data that describes the boundary.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_Boundary






---


### Notes
For more information on this return object and its properties, see SMS_Boundary server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_boundary-server-wmi-class).



---


### Syntax
```PowerShell
Set-CMBoundary [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-NewType {IPSubnet | ADSite | IPV6Prefix | IPRange | Vpn}] [-NewValue <String>] [-PassThru] [-ValueStartsWith <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBoundary [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-NewType {IPSubnet | ADSite | IPV6Prefix | IPRange | Vpn}] [-NewValue <String>] [-PassThru] [-ValueStartsWith <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBoundary [-DisableWildcardHandling] [-ForceWildcardHandling] [-NewName <String>] [-NewType {IPSubnet | ADSite | IPV6Prefix | IPRange | Vpn}] [-NewValue <String>] [-PassThru] -Type {IPSubnet | ADSite | IPV6Prefix | IPRange | Vpn} -Value <String> [-ValueStartsWith <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
