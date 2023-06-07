Remove-CMBoundary
-----------------




### Synopsis
Removes a Configuration Manager boundary.



---


### Description

The Remove-CMBoundary cmdlet removes a boundary from Configuration Manager.



In Configuration Manager, a boundary is an intranet location that contains one or more devices that you can manage. A boundary can be an IP subnet, Active Directory site name, IPv6 prefix, or an IP address range.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBoundary](Get-CMBoundary)



* [New-CMBoundary](New-CMBoundary)



* [Set-CMBoundary](Set-CMBoundary)



* [Remove-CMBoundaryFromGroup](Remove-CMBoundaryFromGroup)



* [Remove-CMBoundaryGroup](Remove-CMBoundaryGroup)





---


### Examples
#### Example 1: Remove a boundary that is specified by its ID
```PowerShell
PS XYZ:\> Remove-CMBoundary -Id "16777223"
```
This command removes the boundary that has an identifier of 16777223. Because the Force parameter is not specified, you must confirm the action before it is performed.
#### Example 2: Remove a boundary by using an InputObject
```PowerShell
PS XYZ:\> $BoundaryObj = Get-CMBoundary -Id "16777223"
PS XYZ:\>
Remove-Boundary -InputObject $BoundaryObj
```
In this example, the first command uses the Get-CMBoundary cmdlet to get a boundary that has the ID of 16777223, and inserts it into the input object $BoundaryObj.


The second command identifies the boundary by using the input object $BoundaryObj and then removes the boundary. Because the Force parameter is not specified, you must confirm the action before it is performed.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of boundary identifiers (IDs).






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |BoundaryId|



#### **InputObject**

Specifies an input object to this cmdlet. You can get the input object by using the Get-CMBoundary cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies an array of boundary names.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |DisplayName|



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
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMBoundary [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundary [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundary [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
