New-CMTaskSequenceGroup
-----------------------




### Synopsis
Creates a Configuration Manager task sequence group.



---


### Description

The New-CMTaskSequenceGroup cmdlet creates a new task sequence group object with specific name, description, options, conditions, and steps/sub-groups.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTaskSequenceGroup](Get-CMTaskSequenceGroup)



* [Set-CMTaskSequenceGroup](Set-CMTaskSequenceGroup)



* [Remove-CMTaskSequenceGroup](Remove-CMTaskSequenceGroup)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> New-CMTaskSequenceGroup -Name $gpName -Description $gpDescription -ContinueOnError -Step ($st1, $st2) -Condition ($cd1, $cd2)
```
The command creates a task sequence group with specific name, description, steps, and conditions.


---


### Parameters
#### **Condition**

Specifies condition objects.






|Type               |Required|Position|PipelineInput|Aliases   |
|-------------------|--------|--------|-------------|----------|
|`[IResultObject[]]`|false   |named   |False        |Conditions|



#### **ContinueOnError**

Indicates whether the creation should continue when there's an error.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Description**

Specifies a description.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Disable**

Indicates whether the step shall be disabled.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|false   |named   |False        |DisableThisStep|



#### **DisableWildcardHandling**

DisableWildcardHandling treats wildcard characters as literal character values. Can't be combined with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

ForceWildcardHandling processes wildcard characters and may lead to unexpected behavior (not recommended). Can't be combined with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specifies the name of a step.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **Step**

Specifies the step objects.






|Type               |Required|Position|PipelineInput|Aliases|
|-------------------|--------|--------|-------------|-------|
|`[IResultObject[]]`|false   |named   |False        |Steps  |



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
* IResultObject#SMS_TaskSequence_Group






---


### Notes




---


### Syntax
```PowerShell
New-CMTaskSequenceGroup [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Step <IResultObject[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
