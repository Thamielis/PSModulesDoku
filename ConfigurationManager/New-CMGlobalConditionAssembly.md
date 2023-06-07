New-CMGlobalConditionAssembly
-----------------------------




### Synopsis
Creates an Assembly type global condition in Configuration Manager.



---


### Description

The New-CMGlobalConditionAssembly cmdlet creates an Assembly type global condition in Configuration Manager.



A global condition is a setting or expression in Configuration Manager that you can use to specify how Configuration Manager provides and deploys an application to clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMGlobalConditionAssembly](Set-CMGlobalConditionAssembly)



* [New-CMGlobalCondition](New-CMGlobalCondition)



* [New-CMGlobalConditionActiveDirectoryQuery](New-CMGlobalConditionActiveDirectoryQuery)



* [New-CMGlobalConditionFile](New-CMGlobalConditionFile)



* [New-CMGlobalConditionIisMetabase](New-CMGlobalConditionIisMetabase)



* [New-CMGlobalConditionOmaUri](New-CMGlobalConditionOmaUri)



* [New-CMGlobalConditionRegistryKey](New-CMGlobalConditionRegistryKey)



* [New-CMGlobalConditionRegistryValue](New-CMGlobalConditionRegistryValue)



* [New-CMGlobalConditionScript](New-CMGlobalConditionScript)



* [New-CMGlobalConditionSqlQuery](New-CMGlobalConditionSqlQuery)



* [New-CMGlobalConditionWqlQuery](New-CMGlobalConditionWqlQuery)



* [New-CMGlobalConditionXPathQuery](New-CMGlobalConditionXPathQuery)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $GlobalAssembly =  New-CMGlobalConditionAssembly -AssemblyName $AssemblyName -Name GC2
```
This command creates an Assembly type global condition in Configuration Manager.


---


### Parameters
#### **AssemblyName**

Specifies the name of the assembly object to search for. The name cannot be the same as any other assembly object of the same type, and the name must be registered in the Global Assembly Cache. The assembly name can be a maximum of 256 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Description**

Specifies a description.






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
New-CMGlobalConditionAssembly -AssemblyName <String> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
