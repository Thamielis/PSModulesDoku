Remove-CMOrchestrationGroup
---------------------------




### Synopsis
Remove an orchestration group.



---


### Description

Use this cmdlet to remove the specified orchestration group.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMOrchestrationGroup](Get-CMOrchestrationGroup)



* [Invoke-CMOrchestrationGroup](Invoke-CMOrchestrationGroup)



* [New-CMOrchestrationGroup](New-CMOrchestrationGroup)



* [Set-CMOrchestrationGroup](Set-CMOrchestrationGroup)



* [About orchestration groups in Configuration Manager](About orchestration groups in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
$og = Get-CMOrchestrationGroup -Name "test OG"

Remove-CMOrchestrationGroup -InputObject $og -Force
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Add this parameter to run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of orchestration group to remove. This value is the MOGID property, which is an integer. For example, `16777217`.






|Type     |Required|Position|PipelineInput|Aliases|
|---------|--------|--------|-------------|-------|
|`[Int32]`|true    |0       |False        |MOGId  |



#### **InputObject**

Specify an object for the orchestration group to remove. To get this object, use the Get-CMOrchestrationGroup (Get-CMOrchestrationGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases           |
|-----------------|--------|--------|--------------|------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|OrchestrationGroup|



#### **Name**

Specify the name of orchestration group to remove.






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|true    |0       |False        |OrchestrationGroupName|



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMOrchestrationGroup [-Id] <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMOrchestrationGroup [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMOrchestrationGroup [-Name] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
