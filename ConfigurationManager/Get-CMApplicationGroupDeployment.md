Get-CMApplicationGroupDeployment
--------------------------------




### Synopsis
Get the deployment of an application group.



---


### Description

Get the deployment of an application group. An app group contains multiple applications, and users see the group in Software Center as a single entity. For more information, see Create application groups (/mem/configmgr/apps/deploy-use/create-app-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMApplicationGroupDeployment](New-CMApplicationGroupDeployment)



* [Remove-CMApplicationGroupDeployment](Remove-CMApplicationGroupDeployment)



* [Set-CMApplicationGroupDeployment](Set-CMApplicationGroupDeployment)



* [Get-CMApplicationGroup](Get-CMApplicationGroup)



* [Create application groups](Create application groups)





---


### Examples
#### Example 1: Get an app group by ID
```PowerShell
Get-CMApplicationGroupDeployment -SmsObjectId "16777536"
```

#### Example 2: Get an app group by deployment ID
```PowerShell
Get-CMApplicationGroupDeployment -DeploymentId "{483392DD-92BF-4CFD-9E21-2BB5F3C01BCD}"
```



---


### Parameters
#### **Collection**

Specify a collection object to which the app group is deployed. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify the ID of the collection to which the app group is deployed. The format is `SMS00001` for example.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the name of the collection to which the app group is deployed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentId**

Specify the ID for the app group deployment. The format of this ID is a standard GUID.






|Type      |Required|Position|PipelineInput|Aliases                                      |
|----------|--------|--------|-------------|---------------------------------------------|
|`[String]`|false   |named   |False        |AssignmentID<br/>ApplicationGroupDeploymentID|



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

Specify an object for the app group. To get this object, use the Get-CMApplicationGroup (Get-CMApplicationGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|false   |named   |True (ByValue)|ApplicationGroup|



#### **Name**

Specify the name for the app group.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |ApplicationGroupName|



#### **SmsObjectId**

Specify the ID of the application group.






|Type     |Required|Position|PipelineInput|Aliases                     |
|---------|--------|--------|-------------|----------------------------|
|`[Int32]`|false   |named   |False        |CI_ID<br/>ApplicationGroupID|



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


* IResultObject[]#SMS_ApplicationGroupAssignment


* IResultObject#SMS_ApplicationGroupAssignment






---


### Notes
This cmdlet returns the following WMI class objects:

- SMS_DeploymentSummary

- SMS_ApplicationGroupAssignment



---


### Syntax
```PowerShell
Get-CMApplicationGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SmsObjectId <Int32>] [-Summary] [<CommonParameters>]
```
