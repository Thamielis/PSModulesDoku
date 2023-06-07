Get-CMDeploymentTypeDetectionClause
-----------------------------------




### Synopsis
Get the detection clauses from the specified deployment type.



---


### Description

Starting in version 2107, use this cmdlet to get the detection clauses from the specified deployment type.



You can use this cmdlet to get a detection clause from one app and apply it to another.



---


### Related Links
* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Set-CMScriptDeploymentType](Set-CMScriptDeploymentType)



* [Set-CMMsiDeploymentType](Set-CMMsiDeploymentType)



* [Set-CMTaskSequenceDeploymentType](Set-CMTaskSequenceDeploymentType)





---


### Examples
#### Example 1: Copy a detection clause between apps
```PowerShell
$appMsi = Get-CMDeploymentType -ApplicationName "CenterApp" -DeploymentTypeName "InterDept - Windows Installer (.msi file)"

$clause1 = Get-CMDeploymentTypeDetectionClause -InputObject $appMsi

Set-CMScriptDeploymentType -ApplicationName "Configuration Manager console" -DeploymentTypeName "Install" -AddDetectionClause $clause1
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



#### **InputObject**

Specify a deployment type object from which to get the detection clause. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* DetectionClause[]


* DetectionClause






---


### Notes




---


### Syntax
```PowerShell
Get-CMDeploymentTypeDetectionClause [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
