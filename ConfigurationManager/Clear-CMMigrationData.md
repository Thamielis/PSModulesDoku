Clear-CMMigrationData
---------------------




### Synopsis
Deletes historical data about a data migration operation.



---


### Description

The Clear-CMMigrationData cmdlet deletes the historical data about a data migration operation. With Configuration Manager, you can migrate data from a supported Configuration Manager hierarchy to a Configuration Manager environment. When you migrate data from a source hierarchy, you access data from the site databases that you identify in the source infrastructure and then transfer that data to your current environment from the database of the destination hierarchy. Clear-CMMigrationData cleans up the historical data from the destination hierarchy database.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMMigrationExclusionList](Set-CMMigrationExclusionList)



* [Set-CMMigrationSource](Set-CMMigrationSource)





---


### Examples
#### Example 1: Clean up historical data from a migration
```PowerShell
PS XYZ:\>Clear-CMMigrationData -SiteCode "C04"
```
This command removes the historical data from the destination site that has the site code C04.


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



#### **SourceSiteCode**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteCode|



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Clear-CMMigrationData [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SourceSiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
