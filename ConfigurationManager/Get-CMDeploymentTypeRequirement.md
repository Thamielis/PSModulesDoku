Get-CMDeploymentTypeRequirement
-------------------------------




### Synopsis
Get the requirement rules for a deployment type.



---


### Description

Use this cmdlet to get the requirement rules for the specified application deployment type. You can use the returned object to add the same rules to another deployment type.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeploymentType](Get-CMDeploymentType)





---


### Examples
#### Example 1: Copy requirement rules between deployment types
```PowerShell
$dt1 = Get-CMDeploymentType -ApplicationName "AppA" -DeploymentTypeName "dt1"

$rule = $dt1 | Get-CMDeploymentTypeRequirement

Set-CMScriptDeploymentType -ApplicationName "AppB" -DeploymentTypeName "dt2" -AddRequirement $rule
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

Specify a deployment type object from which to get the requirement rules. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* Rule[]


* Rule






---


### Notes




---


### Syntax
```PowerShell
Get-CMDeploymentTypeRequirement [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
