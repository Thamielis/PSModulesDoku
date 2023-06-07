New-CMGlobalConditionScript
---------------------------




### Synopsis
Creates a Script type global condition in Configuration Manager.



---


### Description

The New-CMGlobalConditionScript cmdlet creates a Script type global condition in Configuration Manager.



A global condition is a setting or expression in Configuration Manager that you can use to specify how Configuration Manager provides and deploys an application to clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMGlobalConditionScript](Set-CMGlobalConditionScript)



* [New-CMGlobalCondition](New-CMGlobalCondition)



* [New-CMGlobalConditionActiveDirectoryQuery](New-CMGlobalConditionActiveDirectoryQuery)



* [New-CMGlobalConditionAssembly](New-CMGlobalConditionAssembly)



* [New-CMGlobalConditionFile](New-CMGlobalConditionFile)



* [New-CMGlobalConditionIisMetabase](New-CMGlobalConditionIisMetabase)



* [New-CMGlobalConditionOmaUri](New-CMGlobalConditionOmaUri)



* [New-CMGlobalConditionRegistryKey](New-CMGlobalConditionRegistryKey)



* [New-CMGlobalConditionRegistryValue](New-CMGlobalConditionRegistryValue)



* [New-CMGlobalConditionSqlQuery](New-CMGlobalConditionSqlQuery)



* [New-CMGlobalConditionWqlQuery](New-CMGlobalConditionWqlQuery)



* [New-CMGlobalConditionXPathQuery](New-CMGlobalConditionXPathQuery)





---


### Examples
#### Example 1
```PowerShell
$GlobalScript = New-CMGlobalConditionScript -DataType String -ScriptText $string -ScriptLanguage JScript -Name GC5
```
This command creates a Script type global condition in Configuration Manager.


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



#### **FilePath**

Specifies a file path of the script.  You can use Windows PowerShell, VBScript, or JScript scripts.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **ScriptLanguage**

Specifies a script language.



Valid Values:

* PowerShell
* VBScript
* JScript
* ShellScript






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[ScriptingLanguage]`|true    |named   |False        |



#### **ScriptText**

Specifies a script string.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Use32BitHost**

Indicate whether to use 32-bit host.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseLoggedOnUserCredential**

If you enable this option, the script will run on client computers by using the credentials of the user who is signed in.






|Type       |Required|Position|PipelineInput|Aliases                   |
|-----------|--------|--------|-------------|--------------------------|
|`[Boolean]`|false   |named   |False        |UseLoggedOnUserCredentials|





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
New-CMGlobalConditionScript -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean} [-Description <String>] [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] -Name <String> -ScriptLanguage {JScript | PowerShell | VBScript} [-Use32BitHost <Boolean>] [-UseLoggedOnUserCredential <Boolean>] [<CommonParameters>]
```
```PowerShell
New-CMGlobalConditionScript -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean} [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -ScriptLanguage {JScript | PowerShell | VBScript} -ScriptText <String> [-Use32BitHost <Boolean>] [-UseLoggedOnUserCredential <Boolean>] [<CommonParameters>]
```
