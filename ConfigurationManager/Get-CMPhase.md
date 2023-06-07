Get-CMPhase
-----------




### Synopsis
Get a deployment phase for a specific instance of a phased deployment.



---


### Description

Use this cmdlet to get a deployment phase for a specific instance of a phased deployment.



For more information, see Create phased deployments with Configuration Manager (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Create phased deployments](Create phased deployments)





---


### Examples
#### Example 1: Get phase by ID
```PowerShell
Get-CMPhase -Id "66DEDF86-D0CB-457D-88BE-47E3FAC92A47"
```



---


### Parameters
#### **Collection**

Specify a collection object for the phase. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify a collection by ID for the phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify a collection by name for the phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **Id**

Specify the ID of the phase.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |PhaseId|



#### **InputObject**

Specify the phased deployment object for the phase.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |0       |True (ByValue)|PhasedDeployment|



#### **Name**

Specify the name of the phased deployment.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|false   |named   |False        |PhaseName|



#### **Order**

Specify an integer value for the phase's order.






|Type     |Required|Position|PipelineInput|Aliases   |
|---------|--------|--------|-------------|----------|
|`[Int32]`|false   |named   |False        |PhaseOrder|



#### **PhasedDeploymentId**

Specify the ID of the phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **PhasedDeploymentName**

Specify the name of the phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* Microsoft.ConfigurationManager.PhasedDeploymentModel.Phase






---


### Notes




---


### Syntax
```PowerShell
Get-CMPhase [-InputObject] <IResultObject> [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [-Name <String>] [-Order <Int32>] [<CommonParameters>]
```
```PowerShell
Get-CMPhase [-PhasedDeploymentId] <String> [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [-Name <String>] [-Order <Int32>] [<CommonParameters>]
```
```PowerShell
Get-CMPhase [-PhasedDeploymentName] <String> [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [-Name <String>] [-Order <Int32>] [<CommonParameters>]
```
