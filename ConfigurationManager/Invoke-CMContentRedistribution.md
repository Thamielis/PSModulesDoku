Invoke-CMContentRedistribution
------------------------------




### Synopsis
Invokes a content redistribution.



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
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPoint**








|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **DistributionPointGroup**








|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **DistributionPointGroupName**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **DistributionPointName**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases                                                                                                                                                               |
|-----------------|--------|--------|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|`[IResultObject]`|false   |named   |True (ByValue)|Application<br/>Package<br/>BootImage<br/>DeploymentPackage<br/>SoftwareUpdatePackage<br/>DriverPackage<br/>ImagePackage<br/>OperatingSystemInstaller<br/>TaskSequence|



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
Invoke-CMContentRedistribution [-DisableWildcardHandling] [-DistributionPoint <IResultObject[]>] [-DistributionPointGroup <IResultObject[]>] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMContentRedistribution [-DisableWildcardHandling] [-DistributionPoint <IResultObject[]>] [-DistributionPointGroup <IResultObject[]>] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMContentRedistribution [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
