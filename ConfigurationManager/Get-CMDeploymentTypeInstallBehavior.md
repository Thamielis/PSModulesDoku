Get-CMDeploymentTypeInstallBehavior
-----------------------------------




### Synopsis
Get from the specified deployment type the list of executable files that need to close for the app install to succeed.



---


### Description

Starting in version 2107, use this cmdlet to get from the specified application deployment type the list of executable files that need to close for the app install to succeed. For more general information on the install behavior feature, see Check for running executable files (/mem/configmgr/apps/deploy-use/check-for-running-executable-files).



If you use PowerShell to deploy the application, use the AutoCloseExecutable parameter on either New-CMApplicationDeployment (New-CMApplicationDeployment.md) or [Set-CMApplicationDeployment](Set-CMApplicationDeployment.md). This parameter enables the application deployment setting for install behaviors.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeploymentTypeInstallBehavior](Add-CMDeploymentTypeInstallBehavior)



* [Remove-CMDeploymentTypeInstallBehavior](Remove-CMDeploymentTypeInstallBehavior)



* [Set-CMDeploymentTypeInstallBehavior](Set-CMDeploymentTypeInstallBehavior)



* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Set-CMApplicationDeployment](Set-CMApplicationDeployment)





---


### Examples
#### Example 1: Get the install behaviors for a specific deployment type
```PowerShell
$appName = "CenterApp"
$dtName = "InterDept - Windows Installer (.msi file)"
$msi_dt = Get-CMDeploymentType -ApplicationName $appName -DeploymentTypeName $dtName
Get-CMDeploymentTypeInstallBehavior -InputObject $msi_dt
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

Specify an application deployment type object. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* ProcessInformation[]


* ProcessInformation






---


### Notes




---


### Syntax
```PowerShell
Get-CMDeploymentTypeInstallBehavior [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
