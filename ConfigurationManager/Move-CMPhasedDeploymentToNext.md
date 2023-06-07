Move-CMPhasedDeploymentToNext
-----------------------------




### Synopsis
Move the specified phased deployment to the next phase.



---


### Description

Use this cmdlet to move the specified phased deployment to the next phase.



For more information, see Create phased deployments with Configuration Manager (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMPhasedDeploymentStatus](Get-CMPhasedDeploymentStatus)



* [Resume-CMPhasedDeployment](Resume-CMPhasedDeployment)



* [Suspend-CMPhasedDeployment](Suspend-CMPhasedDeployment)



* [Get-CMApplicationPhasedDeployment](Get-CMApplicationPhasedDeployment)



* [Get-CMSoftwareUpdatePhasedDeployment](Get-CMSoftwareUpdatePhasedDeployment)



* [Get-CMTaskSequencePhasedDeployment](Get-CMTaskSequencePhasedDeployment)



* [Create phased deployments with Configuration Manager](Create phased deployments with Configuration Manager)





---


### Examples
#### Example 1: Move to the next phase for the deployment by name
```PowerShell
Move-CMPhasedDeploymentToNext -Name "myPhasedDeploymentName"
```

#### Example 1: Force move to the next phase for an input deployment object
```PowerShell
$myPhasedDeployment | Move-CMPhasedDeploymentToNext -Force
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Force moves the deployment to the next phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the phased deployment ID.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |PhasedDeploymentId|



#### **InputObject**

Specify a phased deployment object. To get this object, use one of the following cmdlets:


* Get-CMApplicationPhasedDeployment (Get-CMApplicationPhasedDeployment.md)- Get-CMSoftwareUpdatePhasedDeployment (Get-CMSoftwareUpdatePhasedDeployment.md)- Get-CMTaskSequencePhasedDeployment (Get-CMTaskSequencePhasedDeployment.md)






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|PhasedDeployment|



#### **Name**

Specify a phased deployment by name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Move-CMPhasedDeploymentToNext [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Move-CMPhasedDeploymentToNext [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Move-CMPhasedDeploymentToNext [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
