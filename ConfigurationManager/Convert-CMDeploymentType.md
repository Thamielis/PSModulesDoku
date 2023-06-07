Convert-CMDeploymentType
------------------------




### Synopsis
Converts the deployment type of a Configuration Manager deployment application.



---


### Description

The Convert-CMDeploymentType cmdlet converts the deployment type of a Configuration Manager application.



A deployment type is contained within an application and contains the information that Configuration Manager requires to install software. A deployment type also contains rules that specify if and how the software is deployed.



This cmdlet allows for getting a native DeploymentType object from an SMS_DeploymentType WMI object instance. Can be combined with Get-CMDeploymentType (Get-CMDeploymentType.md).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Remove-CMDeploymentType](Remove-CMDeploymentType)



* [Set-CMDeploymentType](Set-CMDeploymentType)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $cmdp = Get-CMDeploymentType -ApplicationName "CenterApp"
PS XYZ:\> Convert-CMDeploymentType $cmdp
```
This command gets the deployment type for the application named CenterApp, and then convert the deployment type.


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

Specifies an SMS DeploymentType object. To obtain an SMS DeploymentType object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type        |Required|Position|PipelineInput |Aliases                                                          |
|------------|--------|--------|--------------|-----------------------------------------------------------------|
|`[PSObject]`|true    |named   |True (ByValue)|IResultObject<br/>DeploymentType<br/>ProviderDeploymentTypeObject|





---


### Inputs
System.Management.Automation.PSObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Convert-CMDeploymentType [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <PSObject> [<CommonParameters>]
```
