Invoke-CMForestDiscovery
------------------------




### Synopsis
Starts a forest discovery operation in Active Directory.



---


### Description

The Invoke-CMForestDiscovery cmdlet starts a forest discovery operation in Active Directory. A forest discovery returns a list of Active Directory sites, subnets, and domains.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Invoke a forest discovery operation
```PowerShell
PS XYZ:\>Invoke-CMForestDiscovery -SiteCode "CM4"
```
This command invokes a forest discovery operation in Active Directory starting at the site that has the site code CM4.


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

Specifies the site that is the starting point for the forest discovery operation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* 






---


### Notes




---


### Syntax
```PowerShell
Invoke-CMForestDiscovery [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
