New-CMGlobalConditionWqlQuery
-----------------------------




### Synopsis
Creates a WQL Query type global condition in Configuration Manager.



---


### Description

The New-CMGlobalConditionWqlQuery cmdlet creates a Wql Query type global condition in Configuration Manager.



A global condition is a setting or expression in Configuration Manager that you can use to specify how Configuration Manager provides and deploys an application to clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMGlobalConditionWqlQuery](Set-CMGlobalConditionWqlQuery)



* [New-CMGlobalCondition](New-CMGlobalCondition)



* [New-CMGlobalConditionActiveDirectoryQuery](New-CMGlobalConditionActiveDirectoryQuery)



* [New-CMGlobalConditionAssembly](New-CMGlobalConditionAssembly)



* [New-CMGlobalConditionFile](New-CMGlobalConditionFile)



* [New-CMGlobalConditionIisMetabase](New-CMGlobalConditionIisMetabase)



* [New-CMGlobalConditionOmaUri](New-CMGlobalConditionOmaUri)



* [New-CMGlobalConditionRegistryKey](New-CMGlobalConditionRegistryKey)



* [New-CMGlobalConditionRegistryValue](New-CMGlobalConditionRegistryValue)



* [New-CMGlobalConditionScript](New-CMGlobalConditionScript)



* [New-CMGlobalConditionSqlQuery](New-CMGlobalConditionSqlQuery)



* [New-CMGlobalConditionXPathQuery](New-CMGlobalConditionXPathQuery)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $GlobalWql = New-CMGlobalConditionWqlQuery -DataType String -Class $aa -Property $aa -Namespace root\aaa -Name GC7
```
This command creates a WQL Query type global condition in Configuration Manager.


---


### Parameters
#### **Class**

Specifies the WMI class that will be used to build a WQL query that will be assessed for compliance on client computers.






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



#### **Namespace**

Specifies the WMI namespace that will be used to build a WQL query that will be assessed for compliance on client computers. The default value is Root\cimv2.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Property**

Specifies the WMI property that will be used to build a WQL query that will be assessed for compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **WhereClause**

Specifies a WHERE clause to be applied to the specified namespace, class, and property on client computers.






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
New-CMGlobalConditionWqlQuery -Class <String> -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray} [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Namespace <String>] -Property <String> [-WhereClause <String>] [<CommonParameters>]
```
