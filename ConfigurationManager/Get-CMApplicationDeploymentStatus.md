Get-CMApplicationDeploymentStatus
---------------------------------




### Synopsis
Gets an application deployment status.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
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








|Type             |Required|Position|PipelineInput |Aliases                                  |
|-----------------|--------|--------|--------------|-----------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Application<br/>Deployment<br/>Assignment|



#### **StatusType**





Valid Values:

* SuccessOrInProgress
* Error
* RequirementsNotMet






|Type                               |Required|Position|PipelineInput|
|-----------------------------------|--------|--------|-------------|
|`[ApplicationDeploymentStatusType]`|false   |named   |False        |





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
Get-CMApplicationDeploymentStatus [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-StatusType {SuccessOrInProgress | Error | RequirementsNotMet}] [<CommonParameters>]
```
