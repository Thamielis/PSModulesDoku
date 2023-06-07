Get-CMPhasedDeploymentStatus
----------------------------




### Synopsis
Get the status of a specific phased deployment.



---


### Description

Use this cmdlet to get the status of a specific phased deployment.



For more information, see Create phased deployments with Configuration Manager (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Create phased deployments with Configuration Manager](Create phased deployments with Configuration Manager)





---


### Examples
#### Example 1: Get status by the deployment name
```PowerShell
Get-CMPhasedDeploymentStatus -Name "myPhasedDeploymentName"
```

#### Example 2: Get status of a variable deployment object
```PowerShell
$myPhasedDeployment | Get-CMPhasedDeploymentStatus
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



#### **InputObject**

Specify a phased deployment object.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|PhasedDeployment|



#### **Name**

Specify the name of the phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.Deployments.PhasedDeploymentInfo






---


### Notes




---


### Syntax
```PowerShell
Get-CMPhasedDeploymentStatus [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMPhasedDeploymentStatus [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMPhasedDeploymentStatus [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
