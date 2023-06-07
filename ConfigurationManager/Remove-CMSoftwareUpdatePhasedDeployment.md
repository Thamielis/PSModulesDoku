Remove-CMSoftwareUpdatePhasedDeployment
---------------------------------------




### Synopsis
Use this cmdlet to remove a phased deployment for software updates.



---


### Description

Use this cmdlet to remove a phased deployment for software updates.



---


### Examples
#### Example 1: Remove a phased deployment on an update
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment -SoftwareUpdateName "mySoftwareUpdateName"
```

#### Example 2: Remove a phased deployment on an update group
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment -SoftwareUpdateGroupName "mySoftwareUpdateGroupName"
```

#### Example 3: Remove a phased deployment by name
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment -Name "myPhasedDeploymentName"
```

#### Example 4: Force remove a phased deployment from input
```PowerShell
$myPhasedDeployment | Remove-CMSoftwareUpdatePhasedDeployment -Force
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Force remove the phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the phased deployment to remove. The value is a GUID format.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |PhasedDeploymentId|



#### **InputObject**

Specify an object for the phased deployment to remove.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|PhasedDeployment|



#### **Name**

Specify the name of the phased deployment to remove.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdate**

Remove a phased deployment from the specified software update object.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **SoftwareUpdateGroup**

Remove a phased deployment from the specified software update group object.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **SoftwareUpdateGroupId**

Specify the ID of the software update group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateGroupName**

Specify the name of the software update group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateId**

Specify the ID of the software update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateName**

Specify the name of the software update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdate <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateGroup <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateGroupId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateGroupName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdatePhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
