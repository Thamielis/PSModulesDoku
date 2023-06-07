Remove-CMTaskSequenceDeployment
-------------------------------




### Synopsis
Removes a task sequence deployment from Configuration Manager.



---


### Description

The Remove-CMTaskSequenceDeployment cmdlet removes a task sequence deployment. A task sequence deployment assigns a task sequence to a collection of computers.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequenceDeployment](New-CMTaskSequenceDeployment)



* [Get-CMTaskSequenceDeployment](Get-CMTaskSequenceDeployment)



* [Set-CMTaskSequenceDeployment](Set-CMTaskSequenceDeployment)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> Remove-CMTaskSequenceDeployment -Name "Task Sequence 1333"
```
This command removes a task sequence deployment by name.


---


### Parameters
#### **Collection**

Specifies a collection object.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specifies the ID of a collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specifies a name of a collection designated to receive a task sequence deployment. A collection is a group of client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentId**

Specifies a deployment ID.






|Type      |Required|Position|PipelineInput|Aliases                                     |
|----------|--------|--------|-------------|--------------------------------------------|
|`[String]`|false   |named   |False        |AdvertisementID<br/>TaskSequenceDeploymentID|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a task sequence deployment object. To obtain a task sequence object, use the Get-CMTaskSequenceDeployment (Get-CMTaskSequenceDeployment.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                                                  |
|-----------------|--------|--------|--------------|---------------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Advertisement<br/>TaskSequenceDeployment<br/>TaskSequence|



#### **Name**

Specifies the name of a task sequence.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|false   |named   |False        |TaskSequenceName|



#### **TaskSequenceId**

Specifies the ID of a task sequence.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|false   |named   |False        |Id<br/>TaskSequencePackageId|



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
Remove-CMTaskSequenceDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTaskSequenceDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTaskSequenceDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Name <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTaskSequenceDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-TaskSequenceId <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
