New-CMGlobalConditionActiveDirectoryQuery
-----------------------------------------




### Synopsis
Creates a new Active Directory Query type global condition in Configuration Manager.



---


### Description

The New-CMGlobalConditionActiveDirectoryQuery cmdlet creates a Active Directory Query type global condition in Configuration Manager.



A global condition is a setting or expression in Configuration Manager that you can use to specify how Configuration Manager provides and deploys an application to clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMGlobalConditionActiveDirectoryQuery](Set-CMGlobalConditionActiveDirectoryQuery)



* [New-CMGlobalCondition](New-CMGlobalCondition)



* [New-CMGlobalConditionAssembly](New-CMGlobalConditionAssembly)



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
$GlobalQuery = New-CMGlobalConditionActiveDirectoryQuery -Name GC1 -DataType String -DistinguishedName "CN=Users" -LdapPrefix "LDAP://" -LdapFilter "DC=Vlan123DOM" -Property "DC=net" -SearchScope Base -Description $String
```
This command creates a new Active Directory Query type global condition in Configuration Manager.


---


### Parameters
#### **DataType**

Specifies a global condition data type.



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



#### **DistinguishedName**

Specifies a distinguished name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **LdapFilter**

Specifies a LDAP filter to refine the results from the Active Directory Domain Services query to assess compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **LdapPrefix**

Specifies a valid LDAP prefix to the Active Directory Domain Services query to assess compliance on client computers. You can use either LDAP:// or GC://.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specifies a name for the Active Directory Query global condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Property**

Specifies the property of the Active Directory Domain Services object that will be used to assess compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SearchScope**

Specifies the search scope in Active Directory Domain Services:


* Base - Queries only the specified object. - One Level - This option is not used in this version of Configuration Manager. - Subtree - Queries the specified object and its complete subtree in the directory.



Valid Values:

* Base
* OneLevel
* Subtree






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SearchScope]`|true    |named   |False        |





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
New-CMGlobalConditionActiveDirectoryQuery -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray} [-Description <String>] [-DisableWildcardHandling] -DistinguishedName <String> [-ForceWildcardHandling] -LdapFilter <String> [-LdapPrefix <String>] -Name <String> -Property <String> -SearchScope {Base | OneLevel | Subtree} [<CommonParameters>]
```
