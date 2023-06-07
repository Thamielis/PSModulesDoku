Get-CMConfigurationPolicyDeployment
-----------------------------------




### Synopsis
Get a configuration policy deployment.



---


### Description

Use this cmdlet to get one or more deployments for a configuration policy. These policies include the following types:



- User Data and Profiles



- OneDrive for Business profiles



- Remote Connection profiles



- Company Resource Access



- Microsoft Edge Browser profiles






> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).




---


### Related Links
* [New-CMConfigurationPolicyDeployment](New-CMConfigurationPolicyDeployment)



* [Remove-CMConfigurationPolicyDeployment](Remove-CMConfigurationPolicyDeployment)



* [Set-CMConfigurationPolicyDeployment](Set-CMConfigurationPolicyDeployment)



* [Get-CMConfigurationPolicy](Get-CMConfigurationPolicy)





---


### Examples
#### Example 1: List all configuration policy deployments
```PowerShell
Get-CMConfigurationPolicyDeployment -Fast | Select-Object AssignmentName,AssignmentID
```

#### Example 2: Get all deployments for a configuration policy
```PowerShell
$policy = Get-CMConfigurationPolicy -Name "ODfB policy" -Fast

Get-CMConfigurationPolicyDeployment -InputObject $policy -Fast | Select-Object TargetCollectionID,StartTime,Enabled
```



---


### Parameters
#### **Collection**

Specify a collection object. This collection is the target for the configuration policy deployment. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify a collection ID that's the target for the configuration policy deployment. For example, `XYZ00023`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify a collection name that's the target for the configuration policy deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentId**

Specify the ID of the deployment. This value is a standard GUID, the same as the Deployment ID in the console, and the AssignmentUniqueID attribute on the returned object.






|Type      |Required|Position|PipelineInput|Aliases                                               |
|----------|--------|--------|-------------|------------------------------------------------------|
|`[String]`|false   |named   |False        |AssignmentUniqueID<br/>ConfigurationPolicyDeploymentID|



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

Specify a configuration policy object to get its deployments. To get this object, use the Get-CMConfigurationPolicy (Get-CMConfigurationPolicy.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|false   |named   |True (ByValue)|ConfigurationPolicy|



#### **Name**

Specify the name of a configuration policy to get its deployments.






|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[String]`|false   |named   |False        |ConfigurationPolicyName|



#### **SmsObjectId**

Specify the ID of a configuration policy to get its deployments.






|Type     |Required|Position|PipelineInput|Aliases                        |
|---------|--------|--------|-------------|-------------------------------|
|`[Int32]`|false   |named   |False        |CI_ID<br/>ConfigurationPolicyID|



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


* IResultObject[]#SMS_ConfigurationPolicyAssignment


* IResultObject#SMS_ConfigurationPolicyAssignment






---


### Notes




---


### Syntax
```PowerShell
Get-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-SmsObjectId <Int32>] [-Summary] [<CommonParameters>]
```
