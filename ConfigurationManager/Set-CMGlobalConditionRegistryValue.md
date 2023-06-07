Set-CMGlobalConditionRegistryValue
----------------------------------




### Synopsis
Sets a Registry Value type global condition in Configuration Manager.



---


### Description

The Set-CMGlobalConditionRegistryValue cmdlet modifies settings for a Registry Value type global condition in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMGlobalConditionRegistryValue](New-CMGlobalConditionRegistryValue)



* [Set-CMGlobalCondition](Set-CMGlobalCondition)



* [Set-CMGlobalConditionActiveDirectoryQuery](Set-CMGlobalConditionActiveDirectoryQuery)



* [Set-CMGlobalConditionAssembly](Set-CMGlobalConditionAssembly)



* [Set-CMGlobalConditionFile](Set-CMGlobalConditionFile)



* [Set-CMGlobalConditionIisMetabase](Set-CMGlobalConditionIisMetabase)



* [Set-CMGlobalConditionOmaUri](Set-CMGlobalConditionOmaUri)



* [Set-CMGlobalConditionRegistryKey](Set-CMGlobalConditionRegistryKey)



* [Set-CMGlobalConditionScript](Set-CMGlobalConditionScript)



* [Set-CMGlobalConditionSqlQuery](Set-CMGlobalConditionSqlQuery)



* [Set-CMGlobalConditionWqlQuery](Set-CMGlobalConditionWqlQuery)



* [Set-CMGlobalConditionXPathQuery](Set-CMGlobalConditionXPathQuery)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $GlobalRegValue = Set-CMGlobalConditionRegistryValue -DataType String -KeyName key -Name GC4 -DeviceType WindowsMobile -RegistryHive LocalMachine -ValueName VName
```
This command sets a Registry Value type global condition in Configuration Manager.


---


### Parameters
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



#### **Is64Bit**

Specifies whether the 64-bit registry keys should be searched in addition to the 32-bit registry keys on clients that run a 64-bit version of Windows.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **KeyName**

Specifies the registry key name that you want to search for. The format used should be key\subkey.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **RegistryHive**

Specifies the registry hive that you want to search in.



Valid Values:

* ClassesRoot
* CurrentConfig
* CurrentUser
* LocalMachine
* Users






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[RegistryRootKey]`|false   |named   |False        |



#### **ValueName**

Specifies the value that must be contained within the specified registry key.






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
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMGlobalConditionRegistryValue [-DisableWildcardHandling] [-ForceWildcardHandling] [-Is64Bit <Boolean>] [-KeyName <String>] -Name <String> [-PassThru] [-RegistryHive {ClassesRoot | CurrentConfig | CurrentUser | LocalMachine | Users}] [-ValueName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
