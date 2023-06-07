Get-CMDeploymentTypeReturnCode
------------------------------




### Synopsis
Get the list of return codes from the specified application deployment type.



---


### Description

Starting in version 2107, use this cmdlet to get the list of return codes from the specified application deployment type. For more general information, see Deployment type Return Codes (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-return).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeploymentTypeReturnCode](Add-CMDeploymentTypeReturnCode)



* [Remove-CMDeploymentTypeReturnCode](Remove-CMDeploymentTypeReturnCode)



* [Set-CMDeploymentTypeReturnCode](Set-CMDeploymentTypeReturnCode)



* [Get-CMDeploymentType](Get-CMDeploymentType)





---


### Examples
#### Example 1: List the return codes for the specified deployment type
```PowerShell
$appName = "CenterApp"
$dtName = "InterDept - Windows Installer (.msi file)"
Get-CMDeploymentType -ApplicationName $appName -DeploymentTypeName $dtName | Get-CMDeploymentTypeReturnCode | Format-Table
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

Specify a deployment type object for which to view the return codes. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* ExitCode[]


* ExitCode






---


### Notes




---


### Syntax
```PowerShell
Get-CMDeploymentTypeReturnCode [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
