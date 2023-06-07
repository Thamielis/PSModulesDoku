Get-CMDeploymentTypeSupersedence
--------------------------------




### Synopsis
Get the old deployment types that an application supersedes.



---


### Description

Use this cmdlet to get the old deployment types that an application supersedes.



For more information, see Supersede applications in Configuration Manager (/mem/configmgr/apps/deploy-use/revise-and-supersede-applications#supersedence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMApplicationSupersedence](Set-CMApplicationSupersedence)



* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Supersede applications in Configuration Manager](Supersede applications in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
$dt7 = Get-CMDeploymentType -ApplicationName "LOB app v7" -DeploymentTypeName "Install"
$dt6 = Get-CMDeploymentTypeSupersedence -InputObject $dt7
```
The output of this cmdlet is a deployment type object for LOB app v6 , stored in the dt6 variable.


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

Specify a deployment type object for an application that supersedes another. In other words, the replacement deployment type. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                  |
|-----------------|--------|--------|--------------|-------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SupersedingDeploymentType|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_DeploymentType


* IResultObject#SMS_DeploymentType






---


### Notes
For more information on this return object and its properties, see SMS_SCI_SysResUse server WMI class (/mem/configmgr/develop/reference/apps/sms_deploymenttype-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMDeploymentTypeSupersedence [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
