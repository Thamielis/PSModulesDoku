Get-CMDeploymentType
--------------------




### Synopsis
Get a deployment type for an application.



---


### Description

Use this cmdlet to get a deployment type for a Configuration Manager application.



A deployment type is contained within an application and contains the information that Configuration Manager requires to install software. A deployment type also contains rules that specify if and how the software is deployed.



For more information, see Introduction to application management in Configuration Manager (/mem/configmgr/apps/understand/introduction-to-application-management).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Convert-CMDeploymentType](Convert-CMDeploymentType)



* [Remove-CMDeploymentType](Remove-CMDeploymentType)



* [Set-CMDeploymentType](Set-CMDeploymentType)



* [Get-CMDeploymentTypeRequirement](Get-CMDeploymentTypeRequirement)





---


### Examples
#### Example 1: Get all deployment types for an application
```PowerShell
Get-CMDeploymentType -ApplicationName "CenterApp"
```

#### Example 2: Get a specific deployment type by name
```PowerShell
Get-CMDeploymentType -ApplicationName "CenterApp" -DeploymentTypeName "InterDept - Windows app package (.appx file)"
```



---


### Parameters
#### **ApplicationName**

Specify the name of the application for the deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeploymentTypeId**

Specify the ID of a deployment type to get. This value is the CI_ID , for example: `33554475`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **DeploymentTypeName**

Specify the name of a deployment type to get.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDisplayName|



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

Specify an application object to get its deployment types. To get this object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Application|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_DeploymentType


* IResultObject#SMS_DeploymentType






---


### Notes
For more information on this return object and its properties, see SMS_DeploymentType server WMI class (/mem/configmgr/develop/reference/apps/sms_deploymenttype-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMDeploymentType -ApplicationName <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMDeploymentType -ApplicationName <String> -DeploymentTypeId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMDeploymentType [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
