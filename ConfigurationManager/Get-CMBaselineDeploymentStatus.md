Get-CMBaselineDeploymentStatus
------------------------------




### Synopsis
Get the status of a configuration baseline deployment.



---


### Description

Use this cmdlet to get the status of a configuration baseline deployment.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBaseline](Get-CMBaseline)



* [Get-CMBaselineDeployment](Get-CMBaselineDeployment)



* [New-CMBaselineDeployment](New-CMBaselineDeployment)





---


### Examples
#### Example 1: Show all compliant deployments for a specific configuration baseline
```PowerShell
$baseline = Get-CMBaseline -Name "Check Windows health" -Fast
Get-CMBaselineDeploymentStatus -StatusType Compliant -InputObject $baseline
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an object for a configuration baseline. To get this object, use the Get-CMBaseline (Get-CMBaseline.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                               |
|-----------------|--------|--------|--------------|--------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Baseline<br/>Assignment<br/>Deployment|



#### **StatusType**

Specify a compliance state. For example, to only return compliant deployments, add `-StatusType Compliant`.



Valid Values:

* Unknown
* NonCompliant
* Error
* Compliant






|Type                            |Required|Position|PipelineInput|
|--------------------------------|--------|--------|-------------|
|`[BaselineDeploymentStatusType]`|false   |named   |False        |





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
Get-CMBaselineDeploymentStatus [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -InputObject <IResultObject> [-StatusType {Unknown | NonCompliant | Error | Compliant}] [<CommonParameters>]
```
