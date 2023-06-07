Get-CMTaskSequencePhasedDeployment
----------------------------------




### Synopsis
Get the phased deployment for a task sequence.



---


### Description

Use this cmdlet to get the phased deployment for a task sequence.



For more information, see Create phased deployments with Configuration Manager (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequenceAutoPhasedDeployment](New-CMTaskSequenceAutoPhasedDeployment)



* [Remove-CMTaskSequencePhasedDeployment](Remove-CMTaskSequencePhasedDeployment)



* [Set-CMTaskSequencePhasedDeployment](Set-CMTaskSequencePhasedDeployment)



* [Get-CMPhasedDeploymentStatus](Get-CMPhasedDeploymentStatus)



* [Move-CMPhasedDeploymentToNext](Move-CMPhasedDeploymentToNext)



* [Resume-CMPhasedDeployment](Resume-CMPhasedDeployment)



* [Suspend-CMPhasedDeployment](Suspend-CMPhasedDeployment)



* [Create phased deployments with Configuration Manager](Create phased deployments with Configuration Manager)





---


### Examples
#### Example 1: Get the deployment by name
```PowerShell
Get-CMTaskSequencePhasedDeployment -Name "myPhasedDeploymentName"
```

#### Example 2: Get the deployment by task sequence name
```PowerShell
Get-CMTaskSequencePhasedDeployment -TaskSequenceName "myTaskSequenceName"
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



#### **TaskSequence**

Specify a task sequence object. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **TaskSequenceId**

Specify the ID for a task sequence.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|true    |named   |False        |TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name for a task sequence.






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
Get-CMTaskSequencePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequencePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequencePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -TaskSequence <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequencePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -TaskSequenceId <String> [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequencePhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -TaskSequenceName <String> [<CommonParameters>]
```
