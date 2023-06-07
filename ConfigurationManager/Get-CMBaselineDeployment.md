Get-CMBaselineDeployment
------------------------




### Synopsis
Get a baseline deployment.



---


### Description

Use this cmdlet to get the deployments of configuration baselines.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMBaselineDeployment](New-CMBaselineDeployment)



* [Remove-CMBaselineDeployment](Remove-CMBaselineDeployment)



* [Set-CMBaselineDeployment](Set-CMBaselineDeployment)



* [Get-CMBaseline](Get-CMBaseline)



* [Get-CMBaselineDeploymentStatus](Get-CMBaselineDeploymentStatus)





---


### Examples
#### Example 1: Get all deployments for a configuration baseline
```PowerShell
$baseline = Get-CMBaseline -Name "Check Windows health" -Fast

Get-CMBaselineDeployment -InputObject $baseline
```



---


### Parameters
#### **Collection**

Specify a collection object. This collection is the target for the baseline deployment. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify a collection ID that's the target for the baseline deployment. For example, `XYZ00023`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify a collection name that's the target for the baseline deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentId**

Specify the ID of the deployment. This value is a standard GUID, the same as the Deployment ID in the console.






|Type      |Required|Position|PipelineInput|Aliases                                    |
|----------|--------|--------|-------------|-------------------------------------------|
|`[String]`|false   |named   |False        |AssignmentUniqueID<br/>BaselineDeploymentID|



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

Specify a configuration baseline object to get its deployments. To get this object, use the Get-CMBaseline (Get-CMBaseline.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases |
|-----------------|--------|--------|--------------|--------|
|`[IResultObject]`|false   |named   |True (ByValue)|Baseline|



#### **Name**

Specify the name of a configuration baseline to get its deployments.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |BaselineName|



#### **SmsObjectId**

Specify the ID of a configuration baseline to get its deployments.






|Type     |Required|Position|PipelineInput|Aliases             |
|---------|--------|--------|-------------|--------------------|
|`[Int32]`|false   |named   |False        |CI_ID<br/>BaselineID|



#### **Summary**

Add this parameter to return the SMS_DeploymentSummary WMI class (/mem/configmgr/develop/reference/apps/sms_deploymentsummary-server-wmi-class)object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_DeploymentSummary


* IResultObject#SMS_DeploymentSummary


* IResultObject[]#SMS_BaselineAssignment


* IResultObject#SMS_BaselineAssignment






---


### Notes
For more information on these return objects and their properties, see the following articles:

- SMS_DeploymentSummary server WMI class (/mem/configmgr/develop/reference/apps/sms_deploymentsummary-server-wmi-class)- SMS_BaselineAssignment server WMI class (/mem/configmgr/develop/reference/compliance/sms_baselineassignment-server-wmi-class)



---


### Syntax
```PowerShell
Get-CMBaselineDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMBaselineDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMBaselineDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMBaselineDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-SmsObjectId <Int32>] [-Summary] [<CommonParameters>]
```
