Set-CMDeploymentTypeReturnCode
------------------------------




### Synopsis
Modify return codes for the specified application deployment type.



---


### Description

Starting in version 2107, use this cmdlet to modify return codes for the specified application deployment type. For more general information, see Deployment type Return Codes (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-return).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeploymentTypeReturnCode](Add-CMDeploymentTypeReturnCode)



* [Get-CMDeploymentTypeReturnCode](Get-CMDeploymentTypeReturnCode)



* [Remove-CMDeploymentTypeReturnCode](Remove-CMDeploymentTypeReturnCode)



* [Get-CMDeploymentType](Get-CMDeploymentType)





---


### Examples
#### Example 1: Modify the behavior of the 3010 return code
```PowerShell
$appName = "CenterApp"
$dtName = "InterDept - Windows Installer (.msi file)"
$msi_dt = Get-CMDeploymentType -ApplicationName $appName -DeploymentTypeName $dtName

Add-CMDeploymentTypeReturnCode -InputObject $msi_dt -ReturnCode 3010 -Name "Always reboot" -CodeType HardReboot -Description "Change soft reboot to hard reboot"
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

Specify a deployment type object on which to modify the return code. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



#### **NewName**

Specify a new name to describe this return code.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |ReturnCodeName|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Set-CMDeploymentTypeReturnCode [-CodeType {Failure | Success | FastRetry | HardReboot | SoftReboot}] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] -ReturnCode <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
