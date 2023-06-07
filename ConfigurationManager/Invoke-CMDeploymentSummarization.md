Invoke-CMDeploymentSummarization
--------------------------------




### Synopsis
Runs a Configuration Manager deployment summarization.



---


### Description

The Invoke-CMDeploymentSummarization cmdlet runs a Configuration Manager deployment summarization as soon as possible. Summarization compiles information about current deployment of software from the Configuration Manager site database. By default, Configuration Manager runs this summarization every four hours. If you use this cmdlet to create the summarization immediately, it does not interfere with the regular schedule of creating the current summarization.



You can specify a deployment summarization by ID or by collection or you can specify a deployment summarization object.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Invoke a deployment summarization
```PowerShell
PS XYZ:\>Invoke-CMDeploymentSummarization -CollectionName "CMWest"
```
This command runs a deployment summarization for the collection named CMWest.


---


### Parameters
#### **CollectionId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specifies a name of a collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeploymentId**

Specifies an ID of a deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Specifies a deployment summarization object.






|Type             |Required|Position|PipelineInput |Aliases                         |
|-----------------|--------|--------|--------------|--------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection<br/>DeploymentSummary|



#### **SoftwareName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Invoke-CMDeploymentSummarization -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-SoftwareName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMDeploymentSummarization -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-SoftwareName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMDeploymentSummarization -DeploymentId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-SoftwareName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMDeploymentSummarization [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-SoftwareName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
