Get-CMSoftwareUpdateDeploymentStatus
------------------------------------




### Synopsis
Get the status of a software update deployment.



---


### Description

The Get-CMSoftwareUpdateDeploymentStatus cmdlet gets the status of a software update deployment. Use the Get-CMSoftwareUpdateDeployment cmdlet to get a software update deployment.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateDeployment](Get-CMSoftwareUpdateDeployment)





---


### Examples
#### Example 1: Display deployment status for a Patch Tuesday deployment
```PowerShell
$sudeploy = Get-CMSoftwareUpdateDeployment -Name "Patch Tuesday - Office and Edge 2020-07-15 00:11:11"

Get-CMSoftwareUpdateDeploymentStatus -InputObject $sudeploy
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

Specify a software update deployment object for which to get status. Use the Get-CMSoftwareUpdateDeployment cmdlet to get this object.






|Type             |Required|Position|PipelineInput |Aliases                                     |
|-----------------|--------|--------|--------------|--------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SoftwareUpdate<br/>Assignment<br/>Deployment|





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
Get-CMSoftwareUpdateDeploymentStatus [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
