Set-CMGlobalConditionAssembly
-----------------------------




### Synopsis
Sets an Assembly type global condition in Configuration Manager.



---


### Description

The Set-CMGlobalConditionAssembly cmdlet modifies settings for an Assembly type global condition in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMGlobalConditionAssembly](New-CMGlobalConditionAssembly)



* [Set-CMGlobalCondition](Set-CMGlobalCondition)



* [Set-CMGlobalConditionActiveDirectoryQuery](Set-CMGlobalConditionActiveDirectoryQuery)



* [Set-CMGlobalConditionFile](Set-CMGlobalConditionFile)



* [Set-CMGlobalConditionIisMetabase](Set-CMGlobalConditionIisMetabase)



* [Set-CMGlobalConditionOmaUri](Set-CMGlobalConditionOmaUri)



* [Set-CMGlobalConditionRegistryKey](Set-CMGlobalConditionRegistryKey)



* [Set-CMGlobalConditionRegistryValue](Set-CMGlobalConditionRegistryValue)



* [Set-CMGlobalConditionScript](Set-CMGlobalConditionScript)



* [Set-CMGlobalConditionSqlQuery](Set-CMGlobalConditionSqlQuery)



* [Set-CMGlobalConditionWqlQuery](Set-CMGlobalConditionWqlQuery)



* [Set-CMGlobalConditionXPathQuery](Set-CMGlobalConditionXPathQuery)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $GlobalAssembly =  Set-CMGlobalConditionAssembly -AssemblyName $AssemblyName -Name GC2
```
This command sets an Assembly type global condition in Configuration Manager.


---


### Parameters
#### **AssemblyName**

Specifies the name of the assembly object to search for. The name cannot be the same as any other assembly object of the same type, and the name must be registered in the Global Assembly Cache. The assembly name can be a maximum of 256 characters.






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



#### **Name**

Specifies a name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns the current working object. By default, this cmdlet does not generate any output.






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
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMGlobalConditionAssembly [-AssemblyName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
