New-CMVirtualEnvironmentGroup
-----------------------------




### Synopsis
Creates a virtual environment group.



---


### Description

The New-CMVirtualEnvironmentGroup cmdlet creates a virtual environment group that specifies deployment type items.



A virtual environment allows two or more Microsoft Application Virtualization (App-V) deployment types to share the same file system and registry on client computers. When multiple virtual applications modify the same file system or registry values on a client computer, the application with the highest order takes precedence. When an application is installed or when a client evaluates installed applications, the virtual environment on client computers is added or modified.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Create a virtual environment group
```PowerShell
PS XYZ:\> New-CMVirtualEnvironmentGroup -DeploymentType "Office_Standard" -Name "Office Remote Apps"
```
This command creates a virtual environment group named Office Remote Apps for the deployment type Office_Standard.


---


### Parameters
#### **DeploymentTypeItem**








|Type                    |Required|Position|PipelineInput|Aliases       |
|------------------------|--------|--------|-------------|--------------|
|`[DeploymentTypeItem[]]`|true    |named   |False        |DeploymentType|



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

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type               |Required|Position|PipelineInput |
|-------------------|--------|--------|--------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name for the virtual environment group.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMVirtualEnvironmentGroup -DeploymentTypeItem <DeploymentTypeItem[]> [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMVirtualEnvironmentGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject[]> -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
