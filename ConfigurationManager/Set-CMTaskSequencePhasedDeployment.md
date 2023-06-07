Set-CMTaskSequencePhasedDeployment
----------------------------------




### Synopsis
Configure a phased deployment for a task sequence.



---


### Description

Applies to version 2006 and later. Configure a phased deployment for a task sequence. For more information, see Create phased deployments (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence).



---


### Related Links
* [Get-CMTaskSequencePhasedDeployment](Get-CMTaskSequencePhasedDeployment)



* [New-CMTaskSequenceAutoPhasedDeployment](New-CMTaskSequenceAutoPhasedDeployment)



* [New-CMTaskSequenceManualPhasedDeployment](New-CMTaskSequenceManualPhasedDeployment)



* [Remove-CMTaskSequencePhasedDeployment](Remove-CMTaskSequencePhasedDeployment)



* [Get-CMPhase](Get-CMPhase)



* [New-CMTaskSequencePhase](New-CMTaskSequencePhase)



* [Set-CMTaskSequencePhase](Set-CMTaskSequencePhase)



* [Get-CMPhasedDeploymentStatus](Get-CMPhasedDeploymentStatus)



* [Move-CMPhasedDeploymentToNext](Move-CMPhasedDeploymentToNext)



* [Resume-CMPhasedDeployment](Resume-CMPhasedDeployment)



* [Suspend-CMPhasedDeployment](Suspend-CMPhasedDeployment)



* [Create phased deployments](Create phased deployments)





---


### Examples
#### Example 1: Rename a phased deployment
```PowerShell
$tsPhasedDeployment = Get-CMTaskSequencePhasedDeployment -Name "myPhasedDeployment"

$tsPhasedDeployment | Set-CMTaskSequencePhasedDeployment -NewName "New TS phased deployment" -Description "New description" -PassThru
```

#### Example 2: Add a phase
```PowerShell
$newPhase = New-CMTaskSequencePhase -CollectionName "MyCollection" -PhaseName "MyTSPhase" -UserNotification DisplayAll -AllowRemoteDP $true

Set-CMTaskSequencePhasedDeployment -Id "0bc464d9-e7dd-44c1-a157-3f8be6a79c03" -AddPhases ($newPhase)
```



---


### Parameters
#### **AddPhases**

Use this parameter to add one or more phases to a task sequence phased deployment. Use the New-CMTaskSequencePhase (New-CMTaskSequencePhase.md)cmdlet to create a new phase object.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Phase[]]`|false   |named   |False        |



#### **Description**

Specify an optional description to better identify this task sequence phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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

Specify the ID of the task sequence phased deployment to configure. The format of this value is a GUID.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |PhasedDeploymentId|



#### **InputObject**

Specify an object for an task sequence phased deployment to configure. For example, use the Get-CMTaskSequencePhasedDeployment (Get-CMTaskSequencePhasedDeployment.md)cmdlet to get this object.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|PhasedDeployment|



#### **Name**

Specify the name of the task sequence phased deployment to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Use this parameter to rename the task sequence phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemovePhaseIds**

Remove one or more phases specified by their ID.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **RemovePhaseOrders**

Remove one or more phases specified by their order in the phased deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Int32[]]`|false   |named   |False        |



#### **RemovePhases**

Remove one or more phases from a task sequence phased deployment. Use the Get-CMPhase (Get-CMPhase.md)cmdlet to identify the phase to remove.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Phase[]]`|false   |named   |False        |



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
* IResultObject#SMS_PhasedDeployment






---


### Notes




---


### Syntax
```PowerShell
Set-CMTaskSequencePhasedDeployment [-AddPhases <Phase[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-PassThru] [-RemovePhaseIds <String[]>] [-RemovePhaseOrders <Int32[]>] [-RemovePhases <Phase[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequencePhasedDeployment [-AddPhases <Phase[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-RemovePhaseIds <String[]>] [-RemovePhaseOrders <Int32[]>] [-RemovePhases <Phase[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequencePhasedDeployment [-AddPhases <Phase[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-RemovePhaseIds <String[]>] [-RemovePhaseOrders <Int32[]>] [-RemovePhases <Phase[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
