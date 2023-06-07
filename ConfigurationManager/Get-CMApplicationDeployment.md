Get-CMApplicationDeployment
---------------------------




### Synopsis
Get an application deployment.



---


### Description

Use this cmdlet to get an object for an application deployment. You can use this object to configure or remove the deployment.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMApplicationDeployment](New-CMApplicationDeployment)



* [Remove-CMApplicationDeployment](Remove-CMApplicationDeployment)



* [Set-CMApplicationDeployment](Set-CMApplicationDeployment)





---


### Examples
#### Example 1: Get all deployments for an application
```PowerShell
Get-CMApplicationDeployment -Name 'WebView2 Redist (x64)'
```

#### Example 2: Get a specific deployment by name
```PowerShell
Get-CMApplicationDeployment -Name 'Configuration Manager console' -CollectionName 'CM admins'
```



---


### Parameters
#### **Collection**

Specify a collection object to which the application is deployed. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify the ID of the collection to which the application is deployed. This value is a standard collection ID, for example, `XYZ00034`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the name of the collection to which the collection is deployed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentId**

Specify the deployment ID to get. This value is a GUID. It's the Deployment ID value in the console and the AssignmentUniqueID property of the SMS_ApplicationAssignment WMI class.






|Type      |Required|Position|PipelineInput|Aliases                                       |
|----------|--------|--------|-------------|----------------------------------------------|
|`[String]`|false   |named   |False        |AssignmentUniqueID<br/>ApplicationDeploymentID|



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

Specify an application object to get its deployments. To get this object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|false   |named   |True (ByValue)|Application|



#### **Name**

Specify the name of an application to get its deployments.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |named   |False        |ApplicationName|



#### **SmsObjectId**

Specify the CI_ID of the application to get its deployments. This value is the CI Unique ID in the console, the AssignedCI_UniqueID property of the SMS_ApplicationAssignment WMI class, and the CI_UniqueID property of the SMS_Application WMI class. For example, the format is like `ScopeId_0D7D8B60-F2F9-484A-B9F3-4A8B68D14D59/Application_70659c7c-694b-4563-965f-d82537a1de1b/2`.






|Type     |Required|Position|PipelineInput|Aliases                |
|---------|--------|--------|-------------|-----------------------|
|`[Int32]`|false   |named   |False        |CI_ID<br/>ApplicationID|



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


* IResultObject[]#SMS_ApplicationAssignment


* IResultObject#SMS_ApplicationAssignment






---


### Notes
For more information on these return objects and their properties, see the following articles:

- SMS_DeploymentSummary server WMI class (/mem/configmgr/develop/reference/apps/sms_deploymentsummary-server-wmi-class)- SMS_ApplicationAssignment server WMI class (/mem/configmgr/develop/reference/apps/sms_applicationassignment-server-wmi-class)



---


### Syntax
```PowerShell
Get-CMApplicationDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SmsObjectId <Int32>] [-Summary] [<CommonParameters>]
```
