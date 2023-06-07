Get-CMTaskSequenceDeployment
----------------------------




### Synopsis
Get a task sequence deployment.



---


### Description

Use this cmdlet to get a task sequence deployment. A task sequence deployment assigns a task sequence to a collection of computers. For more information, see Deploy a task sequence in Configuration Manager (/mem/configmgr/osd/deploy-use/deploy-a-task-sequence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequenceDeployment](New-CMTaskSequenceDeployment)



* [Set-CMTaskSequenceDeployment](Set-CMTaskSequenceDeployment)



* [Remove-CMTaskSequenceDeployment](Remove-CMTaskSequenceDeployment)



* [Deploy a task sequence in Configuration Manager](Deploy a task sequence in Configuration Manager)





---


### Examples
#### Example 1: Get all deployments for a task sequence by name
```PowerShell
Get-CMTaskSequenceDeployment -Name "Upgrade to Windows 10 latest"
```

#### Example 2: Get all task sequence deployments to a specific collection
```PowerShell
Get-CMTaskSequenceDeployment -Fast -CollectionId "XYZ00112"
```



---


### Parameters
#### **Collection**

Specify a collection object to which a task sequence is deployed. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify a collection ID to which a task sequence is deployed. This value is a standard collection ID, for example, `XYZ00581`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify a collection name to which a task sequence is deployed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentId**

Specify the ID for the deployment. This value is a standard ID, for example, `XYZ20174`. It's the same value as the Deployment ID property in the console, and the AdvertisementID attribute of the SMS_Advertisement WMI class that this cmdlet returns.






|Type      |Required|Position|PipelineInput|Aliases                                     |
|----------|--------|--------|-------------|--------------------------------------------|
|`[String]`|false   |named   |False        |AdvertisementID<br/>TaskSequenceDeploymentID|



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

Specify a task sequence object to get its deployments. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|false   |named   |True (ByValue)|TaskSequence|



#### **Name**

Specify the name of a task sequence to get its deployments.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|false   |named   |False        |TaskSequenceName|



#### **Summary**

Add this parameter to return the SMS_DeploymentSummary WMI class (/mem/configmgr/develop/reference/apps/sms_deploymentsummary-server-wmi-class)object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the ID of a task sequence to get its deployments. This value is a standard ID, for example, `XYZ00279`.






|Type      |Required|Position|PipelineInput|Aliases                              |
|----------|--------|--------|-------------|-------------------------------------|
|`[String]`|false   |named   |False        |SmsObjectId<br/>TaskSequencePackageID|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_DeploymentSummary


* IResultObject#SMS_DeploymentSummary


* IResultObject[]#SMS_Advertisement


* IResultObject#SMS_Advertisement






---


### Notes
For more information on these return objects and their properties, see the following articles:

- SMS_DeploymentSummary server WMI class (/mem/configmgr/develop/reference/apps/sms_deploymentsummary-server-wmi-class)- SMS_Advertisement server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_advertisement-server-wmi-class)



---


### Syntax
```PowerShell
Get-CMTaskSequenceDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequenceDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequenceDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequenceDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Summary] [-TaskSequenceId <String>] [<CommonParameters>]
```
