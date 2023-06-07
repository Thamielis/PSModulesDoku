New-CMGlobalConditionXPathQuery
-------------------------------




### Synopsis
Creates a XPath Query type global condition in Configuration Manager.



---


### Description

The New-CMGlobalConditionXPathQuery cmdlet creates a XPath Query type global condition in Configuration Manager.



A global condition is a setting or expression in Configuration Manager that you can use to specify how Configuration Manager provides and deploys an application to clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMGlobalConditionXPathQuery](Set-CMGlobalConditionXPathQuery)



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



* [New-CMGlobalConditionWqlQuery](New-CMGlobalConditionWqlQuery)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $GlobalXpath = New-CMGlobalConditionXPathQuery -DataType String -XmlFilePath "c:\A" -XPathQuery "/" -Name GC8
```
This command creates a XPath Query type global condition in Configuration Manager.


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



#### **IncludeSubfolder**

Enable this option if you also want to search any sub-folders under the specified path.






|Type       |Required|Position|PipelineInput|Aliases          |
|-----------|--------|--------|-------------|-----------------|
|`[Boolean]`|false   |named   |False        |IncludeSubfolders|



#### **Is64Bit**

Indicate whether the 64-bit system file location (%windir%\system32) should be searched in addition to the 32-bit system file location (%windir%\syswow64) on Configuration Manager clients that run a 64-bit version of Windows.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specifies a name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **XmlFilePath**

Specifies the path to the XML file on client computers that will be used to assess compliance. Configuration Manager supports the use of all Windows system environment variables and the %USERPROFILE% user variable in the path name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **XmlNamespace**

Specifies namespaces to use during the XPath query.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |XmlNamespaces|



#### **XPathQuery**

Specifies a valid full XML path language (XPath) query to use to assess compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **XPathQueryFilePath**

Specifies an XPath query file path.






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
New-CMGlobalConditionXPathQuery -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean} [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> -XmlFilePath <String> [-XmlNamespace <String[]>] -XPathQuery <String> [<CommonParameters>]
```
```PowerShell
New-CMGlobalConditionXPathQuery -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean} [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> -XmlFilePath <String> [-XmlNamespace <String[]>] -XPathQueryFilePath <String> [<CommonParameters>]
```
