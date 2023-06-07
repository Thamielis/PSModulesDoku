Remove-CMDeploymentTypeInstallBehavior
--------------------------------------




### Synopsis
Remove from the specified deployment type the executable files that need to close for the app install to succeed.



---


### Description

Starting in version 2107, use this cmdlet to remove from the specified application deployment type the executable files that need to close for the app install to succeed. For more general information on the install behavior feature, see Check for running executable files (/mem/configmgr/apps/deploy-use/check-for-running-executable-files).



If you use PowerShell to deploy the application, use the AutoCloseExecutable parameter on either New-CMApplicationDeployment (New-CMApplicationDeployment.md) or [Set-CMApplicationDeployment](Set-CMApplicationDeployment.md). This parameter enables the application deployment setting for install behaviors.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeploymentTypeInstallBehavior](Add-CMDeploymentTypeInstallBehavior)



* [Get-CMDeploymentTypeInstallBehavior](Get-CMDeploymentTypeInstallBehavior)



* [Set-CMDeploymentTypeInstallBehavior](Set-CMDeploymentTypeInstallBehavior)



* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Set-CMApplicationDeployment](Set-CMApplicationDeployment)





---


### Examples
#### Example 1: Remove an executable file as an install behavior
```PowerShell
$appName = "CenterApp"
$dtName = "InterDept - Windows Installer (.msi file)"
$msi_dt = Get-CMDeploymentType -ApplicationName $appName -DeploymentTypeName $dtName
Remove-CMDeploymentTypeInstallBehavior -InputObject $msi_dt -ExeFileName "notepad.exe"
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisplayName**

Specify the friendly name of the install behavior to remove.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ExeFileName**

Specify the name of the executable file to remove from the application deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






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
Remove-CMDeploymentTypeInstallBehavior [-DisableWildcardHandling] [-DisplayName <String>] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeploymentTypeInstallBehavior [-DisableWildcardHandling] [-ExeFileName <String>] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
