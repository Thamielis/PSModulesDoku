Set-CMUpdateGroupDeployment
---------------------------




### Synopsis
Sets an update group deployment.



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
#### **Deployment**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DeploymentName**








|Type      |Required|Position|PipelineInput|Aliases                           |
|----------|--------|--------|-------------|----------------------------------|
|`[String]`|false   |named   |False        |Name<br/>UpdateGroupDeploymentName|



#### **Disable**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Enable**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UpdateGroupDeployment**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **UpdateGroupDeploymentId**








|Type     |Required|Position|PipelineInput|Aliases|
|---------|--------|--------|-------------|-------|
|`[Int32]`|true    |named   |False        |Id     |



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
Set-CMUpdateGroupDeployment -Deployment <IResultObject> [-DisableWildcardHandling] [-Enable] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMUpdateGroupDeployment -Deployment <IResultObject> [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMUpdateGroupDeployment [-DeploymentName <String>] [-DisableWildcardHandling] [-Enable] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMUpdateGroupDeployment [-DeploymentName <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMUpdateGroupDeployment [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] -UpdateGroupDeploymentId <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMUpdateGroupDeployment [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] -UpdateGroupDeployment <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMUpdateGroupDeployment [-DisableWildcardHandling] [-Enable] [-ForceWildcardHandling] -UpdateGroupDeployment <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMUpdateGroupDeployment [-DisableWildcardHandling] [-Enable] [-ForceWildcardHandling] -UpdateGroupDeploymentId <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
