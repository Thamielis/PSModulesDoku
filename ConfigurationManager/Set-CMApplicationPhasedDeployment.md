Set-CMApplicationPhasedDeployment
---------------------------------




### Synopsis
Configure a phased deployment for an application.



---


### Description

Applies to version 2006 and later. Configure a phased deployment for an application. For more information, see Create phased deployments (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence).



---


### Related Links
* [Get-CMApplicationPhasedDeployment](Get-CMApplicationPhasedDeployment)



* [New-CMApplicationAutoPhasedDeployment](New-CMApplicationAutoPhasedDeployment)



* [Remove-CMApplicationPhasedDeployment](Remove-CMApplicationPhasedDeployment)



* [Get-CMPhase](Get-CMPhase)



* [Get-CMPhasedDeploymentStatus](Get-CMPhasedDeploymentStatus)



* [Move-CMPhasedDeploymentToNext](Move-CMPhasedDeploymentToNext)



* [Resume-CMPhasedDeployment](Resume-CMPhasedDeployment)



* [Suspend-CMPhasedDeployment](Suspend-CMPhasedDeployment)



* [Create phased deployments](Create phased deployments)





---


### Examples
#### Example 1: Rename a phased deployment
```PowerShell
$appPhasedDeployment = Get-CMApplicationPhasedDeployment -Name "myPhasedDeploymentName"

$appPhasedDeployment | Set-CMApplicationPhasedDeployment -NewName "New app phased deployment" -PassThru
```

#### Example 2: Change the description
```PowerShell
Set-CMApplicationPhasedDeployment -Id "3b107e52-471b-4c9c-a034-928bcc5f6fc0" -Description "This is an app phased deployment description"
```



---


### Parameters
#### **Description**

Specify an optional description to better identify this application phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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

Specify the ID of the application phased deployment to configure. The format of this value is a GUID.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |PhasedDeploymentId|



#### **InputObject**

Specify an object for an application phased deployment to configure. For example, use the Get-CMApplicationPhasedDeployment (Get-CMApplicationPhasedDeployment.md)cmdlet to get this object.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|PhasedDeployment|



#### **Name**

Specify the name of the application phased deployment to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Use this parameter to rename the application phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






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
* IResultObject#SMS_PhasedDeployment






---


### Notes




---


### Syntax
```PowerShell
Set-CMApplicationPhasedDeployment [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationPhasedDeployment [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationPhasedDeployment [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
