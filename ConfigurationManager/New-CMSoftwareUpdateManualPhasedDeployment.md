New-CMSoftwareUpdateManualPhasedDeployment
------------------------------------------




### Synopsis
Create a phased deployment for software updates.



---


### Description

Use this cmdlet to create a phased deployment for software updates. Before you use this cmdlet, add new customized deployment phases with the cmdlet New-CMSoftwareUpdatePhase (New-CMSoftwareUpdatePhase.md).



For more information, see Create phased deployments with Configuration Manager (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence?toc=/mem/configmgr/sum/toc.json&bc=/mem/configmgr/sum/breadcrumb/toc.json).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdatePhasedDeployment](Get-CMSoftwareUpdatePhasedDeployment)



* [Remove-CMSoftwareUpdatePhasedDeployment](Remove-CMSoftwareUpdatePhasedDeployment)



* [Set-CMSoftwareUpdatePhasedDeployment](Set-CMSoftwareUpdatePhasedDeployment)



* [Get-CMPhasedDeploymentStatus](Get-CMPhasedDeploymentStatus)



* [Move-CMPhasedDeploymentToNext](Move-CMPhasedDeploymentToNext)



* [Resume-CMPhasedDeployment](Resume-CMPhasedDeployment)



* [Suspend-CMPhasedDeployment](Suspend-CMPhasedDeployment)



* [Create phased deployments with Configuration Manager](Create phased deployments with Configuration Manager)





---


### Examples
#### Example 1: Create a deployment for software updates by name
```PowerShell
$phase1 = New-CMSoftwareUpdatePhase -CollectionId "SMSDM001" -PhaseName "test01" -UserNotificationOption DisplaySoftwareCenterOnly
$phase2 = New-CMSoftwareUpdatePhase -CollectionId "SMSDM003" -PhaseName "test02" -UserNotificationOption DisplaySoftwareCenterOnly
New-CMSoftwareUpdateManualPhasedDeployment -SoftwareUpdateNames ("myUpdateA", "myUpdateB") -Name "myPhaseDeployment" -AddPhases ($phase1, $phase2)
```

#### Example 2: Create a deployment for a software update group by name
```PowerShell
$phase3 = New-CMSoftwareUpdatePhase -CollectionId "SMSDM001" -PhaseName "test03" -UserNotificationOption DisplaySoftwareCenterOnly
$phase4 = New-CMSoftwareUpdatePhase -CollectionId "SMSDM003" -PhaseName "test04" -UserNotificationOption DisplaySoftwareCenterOnly
New-CMSoftwareUpdateManualPhasedDeployment -SoftwareUpdateGroupName "myGroup" -Name "myPhaseDeploymentForGroup" -AddPhases ($phase3, $phase4)
```



---


### Parameters
#### **AddPhases**

Specify an array of phases. Use New-CMSoftwareUpdatePhase (New-CMSoftwareUpdatePhase.md)to create the phases.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Phase[]]`|true    |named   |False        |



#### **Description**

Specify a description for the software update phased deployment.






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



#### **Name**

Specify a name for the software update phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateGroup**

Specify an object for a software update group. To get this object, use the Get-CMSoftwareUpdateGroup (Get-CMSoftwareUpdateGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **SoftwareUpdateGroupId**

Specify a software update group by ID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **SoftwareUpdateGroupName**

Specify a software update group by name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **SoftwareUpdateIds**

Specify an array of software update IDs.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |0       |False        |



#### **SoftwareUpdateNames**

Specify an array of software update names.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |0       |False        |



#### **SoftwareUpdates**

Specify an array of software update objects. To get this object, use the Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)cmdlet.






|Type               |Required|Position|PipelineInput |
|-------------------|--------|--------|--------------|
|`[IResultObject[]]`|true    |0       |True (ByValue)|



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



Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]





---


### Outputs
* IResultObject#SMS_PhasedDeployment






---


### Notes
The return object is the SMS_PhasedDeployment server WMI class.



---


### Syntax
```PowerShell
New-CMSoftwareUpdateManualPhasedDeployment [-SoftwareUpdateGroup] <IResultObject> -AddPhases <Phase[]> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateManualPhasedDeployment [-SoftwareUpdateGroupId] <String> -AddPhases <Phase[]> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateManualPhasedDeployment [-SoftwareUpdateGroupName] <String> -AddPhases <Phase[]> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateManualPhasedDeployment [-SoftwareUpdateIds] <String[]> -AddPhases <Phase[]> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateManualPhasedDeployment [-SoftwareUpdateNames] <String[]> -AddPhases <Phase[]> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateManualPhasedDeployment [-SoftwareUpdates] <IResultObject[]> -AddPhases <Phase[]> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
