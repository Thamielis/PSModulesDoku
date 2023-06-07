Remove-CMApplicationGroupDeployment
-----------------------------------




### Synopsis
Remove the deployment of an application group.



---


### Description

Remove the deployment of an application group. An app group contains multiple applications, and users see the group in Software Center as a single entity. For more information, see Create application groups (/mem/configmgr/apps/deploy-use/create-app-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplicationGroupDeployment](Get-CMApplicationGroupDeployment)



* [New-CMApplicationGroupDeployment](New-CMApplicationGroupDeployment)



* [Set-CMApplicationGroupDeployment](Set-CMApplicationGroupDeployment)



* [Get-CMApplicationGroup](Get-CMApplicationGroup)



* [Create application groups](Create application groups)





---


### Examples
#### Example 1
```PowerShell
Get-CMApplicationGroupDeployment -DeploymentId "{483392DD-92BF-4CFD-9E21-2BB5F3C01BCD}" | Remove-CMApplicationGroupDeployment
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

Specify an object for the app group. To get this object, use the Get-CMApplicationGroup (Get-CMApplicationGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                                                       |
|-----------------|--------|--------|--------------|--------------------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Assignment<br/>ApplicationGroupDeployment<br/>ApplicationGroup|



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
Remove-CMApplicationGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Name <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationGroupDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SmsObjectId <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
