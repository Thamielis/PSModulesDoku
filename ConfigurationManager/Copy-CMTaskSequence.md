Copy-CMTaskSequence
-------------------




### Synopsis
Create a copy of an existing task sequence in Configuration Manager.



---


### Description

The Copy-CMTaskSequence cmdlet creates a copy of an existing task sequence in Configuration Manager.



A task sequence performs multiple steps or tasks on a Configuration Manager client computer without user intervention.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequence](New-CMTaskSequence)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [Set-CMTaskSequence](Set-CMTaskSequence)



* [Import-CMTaskSequence](Import-CMTaskSequence)



* [Export-CMTaskSequence](Export-CMTaskSequence)



* [Remove-CMTaskSequence](Remove-CMTaskSequence)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $newTS = Copy-CMTaskSequence -Name "TaskSequence01"
```
This command makes a copy of the task sequence with the name TaskSequence01.


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

Specifies a task sequence ID.






|Type      |Required|Position|PipelineInput|Aliases                            |
|----------|--------|--------|-------------|-----------------------------------|
|`[String]`|true    |named   |False        |PackageId<br/>TaskSequencePackageId|



#### **InputObject**

Specifies a task sequence object.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequence|



#### **Name**

Specifies a task sequence name.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|true    |named   |False        |TaskSequenceName|



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
* IResultObject#SMS_TaskSequencePackage






---


### Notes




---


### Syntax
```PowerShell
Copy-CMTaskSequence [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Copy-CMTaskSequence [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Copy-CMTaskSequence [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
