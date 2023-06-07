Set-CMAppVVirtualEnvironment
----------------------------




### Synopsis
Changes settings for virtual applications that you have deployed by using Configuration Manager.



---


### Description

The Set-CMAppVVirtualEnvironment cmdlet changes settings for one or more Microsoft Application Virtualization (App-V) virtual environment objects from Configuration Manager. You can specify App-V environments by name or ID.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAppVVirtualEnvironment](Get-CMAppVVirtualEnvironment)



* [New-CMAppVVirtualEnvironment](New-CMAppVVirtualEnvironment)



* [Remove-CMAppVVirtualEnvironment](Remove-CMAppVVirtualEnvironment)





---


### Examples
#### Example 1: Change virtual environment settings by using a name
```PowerShell
PS XYZ:\> Set-CMAppVVirtualEnvironment -Name "VMWin03" -SecurityScopeAction RemoveMembership -SecurityScopeName "ClientSecGroup01"
```
This command removes the virtual environment named VMWin03 from the security scope named ClientSecGroup01.


---


### Parameters
#### **AddApplicationGroup**

Specifies an array of application groups to add. Application groups contain multiple App-V deployment types that run in the same environment.






|Type                         |Required|Position|PipelineInput|
|-----------------------------|--------|--------|-------------|
|`[VirtualEnvironmentGroup[]]`|false   |named   |False        |



#### **Description**

Specifies a description for the App-V virtual environment.






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

Specifies an array of IDs of virtual environments.






|Type       |Required|Position|PipelineInput|Aliases       |
|-----------|--------|--------|-------------|--------------|
|`[Int32[]]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a virtual environment object for Configuration Manager. To obtain a virtual environment object, use the Get-CMAppVVirtualEnvironment cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies an array of names of virtual environments.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **NewName**

Specifies a new name for a virtual environment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveApplicationGroup**

Specifies an array of application groups to remove. Application groups contain multiple App-V deployment types that run in the same environment.






|Type                         |Required|Position|PipelineInput|
|-----------------------------|--------|--------|-------------|
|`[VirtualEnvironmentGroup[]]`|false   |named   |False        |



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
Set-CMAppVVirtualEnvironment [-Id] <Int32[]> [-AddApplicationGroup <VirtualEnvironmentGroup[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveApplicationGroup <VirtualEnvironmentGroup[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAppVVirtualEnvironment [-InputObject] <IResultObject> [-AddApplicationGroup <VirtualEnvironmentGroup[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveApplicationGroup <VirtualEnvironmentGroup[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAppVVirtualEnvironment [-Name] <String> [-AddApplicationGroup <VirtualEnvironmentGroup[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveApplicationGroup <VirtualEnvironmentGroup[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
