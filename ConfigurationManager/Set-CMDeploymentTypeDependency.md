Set-CMDeploymentTypeDependency
------------------------------




### Synopsis
Sets a deployment type dependency in Configuration Manager.



---


### Description

The Set-CMDeploymentTypeDependency sets a deployment type as a dependency to a dependency group.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeploymentTypeDependency](Add-CMDeploymentTypeDependency)



* [Get-CMDeploymentTypeDependency](Get-CMDeploymentTypeDependency)



* [Remove-CMDeploymentTypeDependency](Remove-CMDeploymentTypeDependency)





---


### Parameters
#### **DecreasePriority**

Indicates decreasing priority. This action changes the order in which the client evaluates each dependency.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DeploymentTypeDependency**

Specifies a deployment type object.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



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



#### **IncreasePriority**

Indicates increasing priority. This action changes the order in which the client evaluates each dependency.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **InputObject**

Specifies a deployment type dependency group object.






|Type                             |Required|Position|PipelineInput |Aliases|
|---------------------------------|--------|--------|--------------|-------|
|`[DeploymentTypeDependencyGroup]`|true    |named   |True (ByValue)|Group  |



#### **IsAutoInstall**

Indicate whether install automatically.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.AppMan.DeploymentTypeDependencyGroup





---


### Outputs
* IResultObject#SMS_Application






---


### Notes




---


### Syntax
```PowerShell
Set-CMDeploymentTypeDependency -DecreasePriority -DeploymentTypeDependency <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <DeploymentTypeDependencyGroup> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentTypeDependency -DeploymentTypeDependency <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -IncreasePriority -InputObject <DeploymentTypeDependencyGroup> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentTypeDependency -DeploymentTypeDependency <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <DeploymentTypeDependencyGroup> -IsAutoInstall <Boolean> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
