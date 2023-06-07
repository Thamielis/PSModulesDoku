Get-CMBoundary
--------------




### Synopsis
Get a site boundary.



---


### Description

The Get-CMBoundary cmdlet gets a Configuration Manager boundary.



In Configuration Manager, a boundary is a network location that contains one or more devices that you can manage. A boundary can be an IP subnet, Active Directory site name, IPv6 prefix, IP address range, or VPN.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMBoundary](Remove-CMBoundary)



* [New-CMBoundary](New-CMBoundary)



* [Set-CMBoundary](Set-CMBoundary)



* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)



* [Define site boundaries and boundary groups in Configuration Manager](Define site boundaries and boundary groups in Configuration Manager)





---


### Examples
#### Example 1: Get a boundary by its ID
```PowerShell
PS XYZ:\> Get-CMBoundary -Id "67777217"
BoundaryFlags:      0
BoundaryID:         67777217
BoundaryType:       1
CreatedBy:          Contoso\PFuller
CreatedOn           6/10/2012 2:58:56 PM
DefaultSiteCode:
DisplayName:
GroupCount:         0
ModifiedBy:         Contoso\PFuller
ModifiedOn:         9/13/2012  10:04 AM
SiteSystems:
Value:              Default1
```

#### Example 2: Get a boundary by the name of an associated boundary group
```PowerShell
Get-CMBoundary -BoundaryGroupName "BGroup07"
```



---


### Parameters
#### **BoundaryGroupId**

Specify the ID of a boundary group that includes the boundary to get. You can get a boundary group ID by using the Get-CMBoundaryGroup (Get-CMBoundaryGroup.md) cmdlet. This ID is the **GroupID** property on the [SMS_BoundaryGroup](/mem/configmgr/develop/reference/core/servers/configure/sms_boundarygroup-server-wmi-class)object. For example, `33`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|true    |named   |False        |



#### **BoundaryGroupInputObject**

Specify an object for a boundary group that includes the boundary to get. You can get this object by using the Get-CMBoundaryGroup (Get-CMBoundaryGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases      |
|-----------------|--------|--------|-------------|-------------|
|`[IResultObject]`|true    |named   |False        |BoundaryGroup|



#### **BoundaryGroupName**

Specify the name of a boundary group that includes the boundary to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BoundaryId**

Specify the ID of the boundary to get. This ID is the BoundaryID property on the SMS_Boundary (/mem/configmgr/develop/reference/core/servers/configure/sms_boundary-server-wmi-class)object. For example, `23`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[UInt32]`|true    |named   |False        |Id     |



#### **BoundaryName**

Specify the name of the boundary to get. This name is the DisplayName property on the SMS_Boundary (/mem/configmgr/develop/reference/core/servers/configure/sms_boundary-server-wmi-class)object.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |DisplayName<br/>Name|



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





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_Boundary


* IResultObject#SMS_Boundary






---


### Notes




---


### Syntax
```PowerShell
Get-CMBoundary -BoundaryGroupId <UInt32> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMBoundary -BoundaryGroupInputObject <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMBoundary -BoundaryGroupName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMBoundary -BoundaryId <UInt32> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMBoundary [-BoundaryName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
