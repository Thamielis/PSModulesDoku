New-CMGlobalConditionIisMetabase
--------------------------------




### Synopsis
Creates an IIS Metabase type global condition in Configuration Manager.



---


### Description

The New-CMGlobalConditionIisMetabase cmdlet creates an IIS Metabase type global condition in Configuration Manager.



A global condition is a setting or expression in Configuration Manager that you can use to specify how Configuration Manager provides and deploys an application to clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMGlobalConditionIisMetabase](Set-CMGlobalConditionIisMetabase)



* [New-CMGlobalCondition](New-CMGlobalCondition)



* [New-CMGlobalConditionActiveDirectoryQuery](New-CMGlobalConditionActiveDirectoryQuery)



* [New-CMGlobalConditionAssembly](New-CMGlobalConditionAssembly)



* [New-CMGlobalConditionFile](New-CMGlobalConditionFile)



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
$GlobalIIS = New-CMGlobalConditionIisMetabase -DataType String -PropertyId $int -Name GC3
```
This command creates an IIS Metabase type global condition in Configuration Manager.


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



#### **MetabasePath**

Specifies a valid path to the IIS Metabase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specifies a name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PropertyId**

Specifies the numeric property of the IIS Metabase setting.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |





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
New-CMGlobalConditionIisMetabase -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray} [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MetabasePath <String>] -Name <String> -PropertyId <Int32> [<CommonParameters>]
```
