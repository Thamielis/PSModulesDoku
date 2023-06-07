New-CMGlobalConditionRegistryValue
----------------------------------




### Synopsis
Creates a Registry Value type global condition in Configuration Manager.



---


### Description

The New-CMGlobalConditionRegistryValue cmdlet creates a Registry Value type global condition in Configuration Manager.



A global condition is a setting or expression in Configuration Manager that you can use to specify how Configuration Manager provides and deploys an application to clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMGlobalConditionRegistryValue](Set-CMGlobalConditionRegistryValue)



* [New-CMGlobalCondition](New-CMGlobalCondition)



* [New-CMGlobalConditionActiveDirectoryQuery](New-CMGlobalConditionActiveDirectoryQuery)



* [New-CMGlobalConditionAssembly](New-CMGlobalConditionAssembly)



* [New-CMGlobalConditionFile](New-CMGlobalConditionFile)



* [New-CMGlobalConditionIisMetabase](New-CMGlobalConditionIisMetabase)



* [New-CMGlobalConditionOmaUri](New-CMGlobalConditionOmaUri)



* [New-CMGlobalConditionRegistryKey](New-CMGlobalConditionRegistryKey)



* [New-CMGlobalConditionScript](New-CMGlobalConditionScript)



* [New-CMGlobalConditionSqlQuery](New-CMGlobalConditionSqlQuery)



* [New-CMGlobalConditionWqlQuery](New-CMGlobalConditionWqlQuery)



* [New-CMGlobalConditionXPathQuery](New-CMGlobalConditionXPathQuery)





---


### Examples
#### Example 1
```PowerShell
$GlobalRegValue = New-CMGlobalConditionRegistryValue -DataType String -KeyName key -Name GC4 -DeviceType WindowsMobile -RegistryHive LocalMachine -ValueName VName
```
This command creates a Registry Value type global condition in Configuration Manager.


---


### Parameters
#### **DataType**

Specifies a data type.



Valid Values:

* String
* DateTime
* Integer
* FloatingPoint
* Version
* Boolean
* StringArray
* IntegerArray
* Base64
* Xml






|Type                       |Required|Position|PipelineInput|
|---------------------------|--------|--------|-------------|
|`[GlobalConditionDataType]`|true    |named   |False        |



#### **Description**

Specifies a description.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeviceType**

Specifies a device type.



Valid Values:

* Windows
* WindowsMobile






|Type                         |Required|Position|PipelineInput|
|-----------------------------|--------|--------|-------------|
|`[GlobalConditionDeviceType]`|true    |named   |False        |



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
|`[String]`|true    |named   |False        |



#### **Name**

Specifies a name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
New-CMGlobalConditionRegistryValue -DataType {String | DateTime | Integer | FloatingPoint | Version | StringArray} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] [-ForceWildcardHandling] [-Is64Bit <Boolean>] -KeyName <String> -Name <String> [-RegistryHive {ClassesRoot | CurrentConfig | CurrentUser | LocalMachine | Users}] [-ValueName <String>] [<CommonParameters>]
```
