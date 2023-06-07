Set-CMDeploymentTypeInstallBehavior
-----------------------------------




### Synopsis
Modify the executable files that need to close for the app install to succeed.



---


### Description

Starting in version 2107, use this cmdlet to modify the executable files that need to close for the app install to succeed. For more general information on the install behavior feature, see Check for running executable files (/mem/configmgr/apps/deploy-use/check-for-running-executable-files).



If you use PowerShell to deploy the application, use the AutoCloseExecutable parameter on either New-CMApplicationDeployment (New-CMApplicationDeployment.md) or [Set-CMApplicationDeployment](Set-CMApplicationDeployment.md). This parameter enables the application deployment setting for install behaviors.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeploymentTypeInstallBehavior](Add-CMDeploymentTypeInstallBehavior)



* [Get-CMDeploymentTypeInstallBehavior](Get-CMDeploymentTypeInstallBehavior)



* [Remove-CMDeploymentTypeInstallBehavior](Remove-CMDeploymentTypeInstallBehavior)



* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Set-CMApplicationDeployment](Set-CMApplicationDeployment)





---


### Examples
#### Example 1: Change the executable file install behavior
```PowerShell
$appName = "CenterApp"
$dtName = "InterDept - Windows Installer (.msi file)"
$msi_dt = Get-CMDeploymentType -ApplicationName $appName -DeploymentTypeName $dtName
Set-CMDeploymentTypeInstallBehavior -InputObject $msi_dt -ExeFileName "notepad.exe" -NewExeFileName "calc.exe" -DisplayName "Calculator"
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisplayName**

Specify a friendly name for the specified executable to help you identify it.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ExeFileName**

Specify the name of the target executable file. To change this executable file, use the NewExeFileName parameter. To change the friendly name, use the DisplayName parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an application deployment type object to modify this setting. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



#### **NewExeFileName**

Specify the name of the new target executable file. The Configuration Manager client checks if this file name is running.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
* IResultObject#SMS_Application






---


### Notes
For more information on this return object and its properties, see SMS_Application server WMI class (/mem/configmgr/develop/reference/apps/sms_application-server-wmi-class).



---


### Syntax
```PowerShell
Set-CMDeploymentTypeInstallBehavior [-DisableWildcardHandling] [-DisplayName <String>] -ExeFileName <String> [-ForceWildcardHandling] -InputObject <IResultObject> [-NewExeFileName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
