Get-CMSoftwareUpdatePhasedDeployment
------------------------------------




### Synopsis
Get the phased deployment for software updates.



---


### Description

Use this cmdlet to get the phased deployment for software updates.



For more information, see Create phased deployments with Configuration Manager (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence?toc=/mem/configmgr/sum/toc.json&bc=/mem/configmgr/sum/breadcrumb/toc.json).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMSoftwareUpdateAutoPhasedDeployment](New-CMSoftwareUpdateAutoPhasedDeployment)



* [Remove-CMSoftwareUpdatePhasedDeployment](Remove-CMSoftwareUpdatePhasedDeployment)



* [Set-CMSoftwareUpdatePhasedDeployment](Set-CMSoftwareUpdatePhasedDeployment)



* [Get-CMPhasedDeploymentStatus](Get-CMPhasedDeploymentStatus)



* [Move-CMPhasedDeploymentToNext](Move-CMPhasedDeploymentToNext)



* [Resume-CMPhasedDeployment](Resume-CMPhasedDeployment)



* [Suspend-CMPhasedDeployment](Suspend-CMPhasedDeployment)



* [Create phased deployments with Configuration Manager](Create phased deployments with Configuration Manager)





---


### Examples
#### Example 1: Get deployment by name
```PowerShell
Get-CMSoftwareUpdatePhasedDeployment -Name "myPhasedDeploymentName"
```

#### Example 2: Get deployment by software update name
```PowerShell
Get-CMSoftwareUpdatePhasedDeployment -SoftwareUpdateName "myUpdateName"
```



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

Specify the ID of the phased deployment.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |PhasedDeploymentId|



#### **Name**

Specify the name of the phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdate**

Specify a software update object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SoftwareUpdateGroup**

Specify a software update group object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SoftwareUpdateGroupId**

Specify the ID of a software update group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateGroupName**

Specify the name of a software update group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateId**

Specify the ID of a software update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateName**

Specify the name of a software update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_PhasedDeployment


* IResultObject[]#SMS_PhasedDeployment






---


### Notes
The return object is the SMS_PhasedDeployment server WMI class.



---


### Syntax
```PowerShell
Get-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdate <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateGroup <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateGroupId <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateGroupName <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateId <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateName <String> [<CommonParameters>]
```
