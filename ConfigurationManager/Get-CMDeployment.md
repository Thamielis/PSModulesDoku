Get-CMDeployment
----------------




### Synopsis
Get a Configuration Manager deployment.



---


### Description

The Get-CMDeployment cmdlet gets one or more Configuration Manager deployments. The cmdlet gets summary information about deployments of applications, software updates, or classic programs.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMPackageDeploymentStatus](Get-CMPackageDeploymentStatus)



* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Remove-CMDeployment](Remove-CMDeployment)



* [Set-CMDeploymentType](Set-CMDeploymentType)





---


### Examples
#### Example 1: Get a deployment for a collection
```PowerShell
Get-CMDeployment -CollectionName "deviceCol1" -FeatureType "Application"
```



---


### Parameters
#### **CollectionName**

Specifies the name of the collection associated with the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentId**

Specifies the ID of a deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FeatureType**

Specifies the feature type of the deployment.



Valid Values:

* Application
* Package
* SoftwareUpdate
* ConfigurationItem
* TaskSequence
* FirewallSetting
* ApplicationGroup






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[DeploymentFeature]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ProgramName**

Specifies the name of the program associated with the deployment. Use this parameter with a legacy distribution program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SoftwareName**

Specifies the name of the software associated with the deployment. Use this parameter with a software update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_DeploymentSummary


* IResultObject#SMS_DeploymentSummary






---


### Notes




---


### Syntax
```PowerShell
Get-CMDeployment [-CollectionName <String>] [-DisableWildcardHandling] [-FeatureType {Application | Package | SoftwareUpdate | ConfigurationItem | TaskSequence | FirewallSetting | ApplicationGroup}] [-ForceWildcardHandling] [-ProgramName <String>] [-SoftwareName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDeployment -DeploymentId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
