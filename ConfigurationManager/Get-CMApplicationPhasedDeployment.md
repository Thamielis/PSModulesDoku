Get-CMApplicationPhasedDeployment
---------------------------------




### Synopsis
Get a phased deployment for an application.



---


### Description

Use this cmdlet to get a phased deployment for an application.



For more information, see Create phased deployments with Configuration Manager (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence?toc=/mem/configmgr/apps/toc.json&bc=/mem/configmgr/apps/breadcrumb/toc.json).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMApplicationAutoPhasedDeployment](New-CMApplicationAutoPhasedDeployment)



* [Remove-CMApplicationPhasedDeployment](Remove-CMApplicationPhasedDeployment)



* [Set-CMApplicationPhasedDeployment](Set-CMApplicationPhasedDeployment)



* [Get-CMPhasedDeploymentStatus](Get-CMPhasedDeploymentStatus)



* [Move-CMPhasedDeploymentToNext](Move-CMPhasedDeploymentToNext)



* [Resume-CMPhasedDeployment](Resume-CMPhasedDeployment)



* [Suspend-CMPhasedDeployment](Suspend-CMPhasedDeployment)



* [Create phased deployments with Configuration Manager](Create phased deployments with Configuration Manager)





---


### Examples
#### Example 1: Get phased deployment by name
```PowerShell
Get-CMApplicationPhasedDeployment -Name "myPhasedDeploymentName"
```

#### Example 2: Get phased deployment by app name
```PowerShell
Get-CMApplicationPhasedDeployment -ApplicationName "myApplicationName"
```



---


### Parameters
#### **Application**

Specify an object for the application. To get this object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **ApplicationId**

Specify the application ID.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |CIId<br/>CI_ID|



#### **ApplicationName**

Specify the application name.






|Type      |Required|Position|PipelineInput|Aliases                        |
|----------|--------|--------|-------------|-------------------------------|
|`[String]`|true    |named   |False        |ApplicationLocalizedDisplayName|



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

Specify the ID of the phased deployment.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |PhasedDeploymentId|



#### **Name**

Specify the name of the phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_PhasedDeployment


* IResultObject[]#SMS_PhasedDeployment






---


### Notes
The return object is the SMS_PhasedDeployment server WMI class.



---


### Syntax
```PowerShell
Get-CMApplicationPhasedDeployment -Application <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationPhasedDeployment -ApplicationId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationPhasedDeployment -ApplicationName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationPhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMApplicationPhasedDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
