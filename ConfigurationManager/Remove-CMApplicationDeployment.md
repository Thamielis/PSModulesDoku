Remove-CMApplicationDeployment
------------------------------




### Synopsis
Remove an application deployment.



---


### Description

Use this cmdlet to remove an application deployment.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplicationDeployment](Get-CMApplicationDeployment)



* [New-CMApplicationDeployment](New-CMApplicationDeployment)



* [Set-CMApplicationDeployment](Set-CMApplicationDeployment)





---


### Examples
#### Example 1
```PowerShell
Remove-CMApplicationDeployment -Name 'Central app' -CollectionName 'All HR devices'
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

Specify the deployment ID to remove. This value is a GUID. It's the Deployment ID value in the console and the AssignmentUniqueID property of the SMS_ApplicationAssignment WMI class.






|Type      |Required|Position|PipelineInput|Aliases                                       |
|----------|--------|--------|-------------|----------------------------------------------|
|`[String]`|false   |named   |False        |AssignmentUniqueID<br/>ApplicationDeploymentID|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an application deployment object to remove. To get this object, use the Get-CMApplicationDeployment (Get-CMApplicationDeployment.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                                             |
|-----------------|--------|--------|--------------|----------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Assignment<br/>ApplicationDeployment<br/>Application|



#### **Name**

Specify the name of the application that's deployed.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |named   |False        |ApplicationName|



#### **SmsObjectId**

Specify the CI_ID of the application that's deployed. This value is the CI Unique ID in the console, the AssignedCI_UniqueID property of the SMS_ApplicationAssignment WMI class, and the CI_UniqueID property of the SMS_Application WMI class. For example, the format is like `ScopeId_0D7D8B60-F2F9-484A-B9F3-4A8B68D14D59/Application_70659c7c-694b-4563-965f-d82537a1de1b/2`.






|Type     |Required|Position|PipelineInput|Aliases                |
|---------|--------|--------|-------------|-----------------------|
|`[Int32]`|false   |named   |False        |CI_ID<br/>ApplicationID|



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


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
Remove-CMApplicationDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Name <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SmsObjectId <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
