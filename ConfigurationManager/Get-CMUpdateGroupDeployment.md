Get-CMUpdateGroupDeployment
---------------------------




### Synopsis
Gets an update group deployment.



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
#### **Collection**








|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentId**








|Type      |Required|Position|PipelineInput|Aliases                                                                           |
|----------|--------|--------|-------------|----------------------------------------------------------------------------------|
|`[String]`|false   |named   |False        |AssignmentUniqueID<br/>UpdateGroupDeploymentID<br/>SoftwareUpdateGroupDeploymentID|



#### **DeploymentName**








|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|false   |named   |False        |UpdateGroupDeploymentName|



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








|Type             |Required|Position|PipelineInput |Aliases                            |
|-----------------|--------|--------|--------------|-----------------------------------|
|`[IResultObject]`|false   |named   |True (ByValue)|UpdateGroup<br/>SoftwareUpdateGroup|



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases                                    |
|----------|--------|--------|-------------|-------------------------------------------|
|`[String]`|false   |named   |False        |UpdateGroupName<br/>SoftwareUpdateGroupName|



#### **SmsObjectId**








|Type     |Required|Position|PipelineInput|Aliases                                          |
|---------|--------|--------|-------------|-------------------------------------------------|
|`[Int32]`|false   |named   |False        |CI_ID<br/>UpdateGroupID<br/>SoftwareUpdateGroupID|



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
* IResultObject[]#SMS_UpdateGroupAssignment


* IResultObject#SMS_UpdateGroupAssignment


* IResultObject[]#SMS_DeploymentSummary


* IResultObject#SMS_DeploymentSummary






---


### Notes
For more information on these return objects and their properties, see the following articles:

- SMS_DeploymentSummary server WMI class (/mem/configmgr/develop/reference/apps/sms_deploymentsummary-server-wmi-class)- SMS_UpdateGroupAssignment server WMI class (/mem/configmgr/develop/reference/sum/sms_updategroupassignment-server-wmi-class)



---


### Syntax
```PowerShell
Get-CMUpdateGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMUpdateGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMUpdateGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMUpdateGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SmsObjectId <Int32>] [-Summary] [<CommonParameters>]
```
