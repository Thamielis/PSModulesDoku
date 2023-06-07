Add-CMDeploymentTypeReturnCode
------------------------------




### Synopsis
Add return codes to a supported application deployment type.



---


### Description

Starting in version 2107, use this cmdlet to add return codes to a supported application deployment type. For more general information, see Deployment type Return Codes (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-return).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeploymentTypeReturnCode](Get-CMDeploymentTypeReturnCode)



* [Remove-CMDeploymentTypeReturnCode](Remove-CMDeploymentTypeReturnCode)



* [Set-CMDeploymentTypeReturnCode](Set-CMDeploymentTypeReturnCode)



* [Get-CMDeploymentType](Get-CMDeploymentType)





---


### Examples
#### Example 1: Add return code 1602 to an MSI deployment type
```PowerShell
$appName = "CenterApp"
$dtName = "InterDept - Windows Installer (.msi file)"
$msi_dt = Get-CMDeploymentType -ApplicationName $appName -DeploymentTypeName $dtName

Add-CMDeploymentTypeReturnCode -InputObject $msi_dt -ReturnCode 1602 -Name "User cancel" -CodeType Failure -Description "The user cancelled the installation"
```



---


### Parameters
#### **CodeType**

Specify the type of return code. This setting defines how Configuration Manager interprets the specified return code from this deployment type. The available types vary based on the deployment type technology.


* `Failure`: The deployment type failed to install.


* `Success`: The deployment type successfully installed, and no reboot is necessary.


* `FastRetry`: Another installation is already in progress on the device. The client retries every two hours, for a total of 10 times.


* `HardReboot`: The deployment type successfully installed, but requires the device to restart. Nothing else can be installed until the device restarts.


* `SoftReboot`: The deployment type successfully installed, but requests the device to restart. Other installations can occur before the device restarts.



Valid Values:

* Failure
* Success
* FastRetry
* HardReboot
* SoftReboot






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[ExitCodeClass]`|false   |named   |False        |



#### **Description**

Specify an optional description to help you identify and describe this return code.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|false   |named   |False        |ReturnCodeDescription|



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

Specify a deployment type object on which to add the return code. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



#### **Name**

Specify an optional name to describe this return code.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |ReturnCodeName|



#### **ReturnCode**

Specify an integer value for the return code that you expect from this deployment type. This value is any positive or negative integer between `-2147483648` and `2147483647`.






|Type     |Required|Position|PipelineInput|Aliases        |
|---------|--------|--------|-------------|---------------|
|`[Int32]`|true    |named   |False        |ReturnCodeValue|



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
Add-CMDeploymentTypeReturnCode [-CodeType {Failure | Success | FastRetry | HardReboot | SoftReboot}] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Name <String>] -ReturnCode <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
