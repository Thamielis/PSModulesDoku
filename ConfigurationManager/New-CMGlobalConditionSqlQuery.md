New-CMGlobalConditionSqlQuery
-----------------------------




### Synopsis
Creates a SQL Query type global condition in Configuration Manager.



---


### Description

The New-CMGlobalConditionSqlQuery cmdlet creates a SQL Query type global condition in Configuration Manager.



A global condition is a setting or expression in Configuration Manager that you can use to specify how Configuration Manager provides and deploys an application to clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMGlobalConditionSqlQuery](Set-CMGlobalConditionSqlQuery)



* [New-CMGlobalCondition](New-CMGlobalCondition)



* [New-CMGlobalConditionActiveDirectoryQuery](New-CMGlobalConditionActiveDirectoryQuery)



* [New-CMGlobalConditionAssembly](New-CMGlobalConditionAssembly)



* [New-CMGlobalConditionFile](New-CMGlobalConditionFile)



* [New-CMGlobalConditionIisMetabase](New-CMGlobalConditionIisMetabase)



* [New-CMGlobalConditionOmaUri](New-CMGlobalConditionOmaUri)



* [New-CMGlobalConditionRegistryKey](New-CMGlobalConditionRegistryKey)



* [New-CMGlobalConditionRegistryValue](New-CMGlobalConditionRegistryValue)



* [New-CMGlobalConditionScript](New-CMGlobalConditionScript)



* [New-CMGlobalConditionWqlQuery](New-CMGlobalConditionWqlQuery)



* [New-CMGlobalConditionXPathQuery](New-CMGlobalConditionXPathQuery)





---


### Examples
#### Example 1
```PowerShell
$GlobalSql = New-CMGlobalConditionSqlQuery -DataType String -QueryText $string -Database ss -Column aa -Name GC6
```
This command creates a SQL Query type global condition in Configuration Manager.


---


### Parameters
#### **AllInstances**

Indicates that the global condition searches all database instances. To search a named instance, specify the InstanceName parameter. To search the default instance, specify the UseDefaultInstance parameter.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|false   |named   |False        |UseAllInstances|



#### **Column**

Specifies the column name used to assess the compliance of the global condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Database**

Specifies a database name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **FilePath**

Specifies a file path.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InstanceName**

Specifies a instance where you want to run the SQL Query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specifies a name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **QueryText**

Specifies the full SQL query to use for the global condition.






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
New-CMGlobalConditionSqlQuery [-AllInstances] -Column <String> -Database <String> -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean} [-Description <String>] [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] [-InstanceName <String>] -Name <String> [<CommonParameters>]
```
```PowerShell
New-CMGlobalConditionSqlQuery [-AllInstances] -Column <String> -Database <String> -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean} [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InstanceName <String>] -Name <String> -QueryText <String> [<CommonParameters>]
```
