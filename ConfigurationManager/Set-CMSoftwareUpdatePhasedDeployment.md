Set-CMSoftwareUpdatePhasedDeployment
------------------------------------




### Synopsis
Configure a phased deployment for a software update.



---


### Description

Applies to version 2006 and later. Configure a phased deployment for a software update. For more information, see Create phased deployments (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence).



---


### Related Links
* [Get-CMSoftwareUpdatePhasedDeployment](Get-CMSoftwareUpdatePhasedDeployment)



* [New-CMSoftwareUpdateAutoPhasedDeployment](New-CMSoftwareUpdateAutoPhasedDeployment)



* [New-CMSoftwareUpdateManualPhasedDeployment](New-CMSoftwareUpdateManualPhasedDeployment)



* [Remove-CMSoftwareUpdatePhasedDeployment](Remove-CMSoftwareUpdatePhasedDeployment)



* [Get-CMPhase](Get-CMPhase)



* [New-CMSoftwareUpdatePhase](New-CMSoftwareUpdatePhase)



* [Set-CMSoftwareUpdatePhase](Set-CMSoftwareUpdatePhase)



* [Get-CMPhasedDeploymentStatus](Get-CMPhasedDeploymentStatus)



* [Move-CMPhasedDeploymentToNext](Move-CMPhasedDeploymentToNext)



* [Resume-CMPhasedDeployment](Resume-CMPhasedDeployment)



* [Suspend-CMPhasedDeployment](Suspend-CMPhasedDeployment)



* [Create phased deployments](Create phased deployments)





---


### Examples
#### Example 1: Rename a phased deployment
```PowerShell
$suPhasedDeployment = Get-CMSoftwareUpdatePhasedDeployment -Name "myPhasedDeployment"

$suPhasedDeployment | Set-CMSoftwareUpdatePhasedDeployment -NewName "New SU phased deployment" -Description "New description" -PassThru
```

#### Example 2: Add a phase
```PowerShell
$newPhase = New-CMSoftwareUpdatePhase -CollectionName "MyCollection" -PhaseName "MySUPhase" -UserNotificationOption DisplaySoftwareCenterOnly

Set-CMSoftwareUpdatePhasedDeployment -Id "da0a01a3-b7ea-4d4b-8392-94b39ecabf8b" -AddPhases ($newPhase)
```



---


### Parameters
#### **AddPhases**

Use this parameter to add one or more phases to a software update phased deployment. Use the New-CMSoftwareUpdatePhase (New-CMSoftwareUpdatePhase.md)cmdlet to create a new phase object.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Phase[]]`|false   |named   |False        |



#### **Description**

Specify an optional description to better identify this software update phased deployment.






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

Specify the ID of the software update phased deployment to configure. The format of this value is a GUID.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |PhasedDeploymentId|



#### **InputObject**

Specify an object for an software update phased deployment to configure. For example, use the Get-CMSoftwareUpdatePhasedDeployment (Get-CMSoftwareUpdatePhasedDeployment.md)cmdlet to get this object.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|PhasedDeployment|



#### **Name**

Specify the name of the software update phased deployment to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Use this parameter to rename the software update phased deployment.






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

Remove one or more phases from a software update phased deployment. Use the Get-CMPhase (Get-CMPhase.md)cmdlet to identify the phase to remove.






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
Set-CMSoftwareUpdatePhasedDeployment [-AddPhases <Phase[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-PassThru] [-RemovePhaseIds <String[]>] [-RemovePhaseOrders <Int32[]>] [-RemovePhases <Phase[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdatePhasedDeployment [-AddPhases <Phase[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-RemovePhaseIds <String[]>] [-RemovePhaseOrders <Int32[]>] [-RemovePhases <Phase[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdatePhasedDeployment [-AddPhases <Phase[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-RemovePhaseIds <String[]>] [-RemovePhaseOrders <Int32[]>] [-RemovePhases <Phase[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
