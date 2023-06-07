New-CMGlobalCondition
---------------------




### Synopsis
Creates a Configuration Manager global condition object.



---


### Description

The New-CMGlobalCondition cmdlet creates a global condition in Configuration Manager.



A global condition is a setting or expression in Configuration Manager that you can use to specify how Configuration Manager provides and deploys an application to clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMGlobalCondition](Get-CMGlobalCondition)



* [Set-CMGlobalCondition](Set-CMGlobalCondition)



* [Remove-CMGlobalCondition](Remove-CMGlobalCondition)





---


### Examples
#### Example 1: Create a global condition
```PowerShell
PS XYZ:\> New-CMGlobalCondition -AssemblyName "Microsoft.Office.Tools.Word.v9.0" -DeviceType $Windows
```
This command creates a global condition that searches the assembly named Microsoft.Office.Tools.Word.v9.0 on Windows devices.


---


### Parameters
#### **AllInstances**

Indicates that the global condition searches all database instances. To search a named instance, specify the InstanceName parameter. To search the default instance, specify the UseDefaultInstance parameter.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|true    |named   |False        |UseAllInstances|



#### **AssemblyName**

Specifies the name of an assembly for which to search. An assembly name must be registered in the Global Assembly Cache.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Class**

Specifies a Windows Management Instrumentation (WMI) class used to build a WMI Query Language (WQL) query. The query assesses compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Column**

Specifies the column name used to assess the compliance of the global condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Database**

Specifies the name of a database. The SQL query runs on this database.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DataType**

Specifies the global condition data type. The acceptable values for this parameter are:


* Boolean


* DateTime


* FloatingPoint


* Integer


* IntegerArray


* String


* StringArray


* Version



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



#### **DefaultInstance**

Indicates that the global condition searches the default database instance. To search a named instance, specify the InstanceName parameter. To search all instances, specify the UseAllInstances parameter.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Switch]`|true    |named   |False        |UseDefaultInstance|



#### **Description**

Specifies a description for the global condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeviceType**

Specifies the type of device to which this global condition applies. The acceptable values for this parameter are: Nokia, Windows, and WindowsMobile.



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



#### **DistinguishedName**

Specifies the distinguished name of the Active Directory Domain Services (AD DS) object to assess for compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **FileOrFolderName**

Specifies the name of a file or folder. Specify the IsFolder parameter to search for a folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **FilePath**

Specifies a file path for the file that the condition assesses for compliance.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IncludeSubfolder**

Indicates whether the cmdlet includes subfolders in the operation.






|Type       |Required|Position|PipelineInput|Aliases          |
|-----------|--------|--------|-------------|-----------------|
|`[Boolean]`|false   |named   |False        |IncludeSubfolders|



#### **InstanceName**

Specifies the name of a database instance that the global condition searches. To search the default instance, specify the UseDefaultInstance parameter. To search all instances, specify the UseAllInstances parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Is64Bit**

Indicates that the global condition searches the 64-bit system file location in addition to the 32-bit system file location.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsFolder**

Indicates that the global condition searches for a folder. If you do not select this parameter, the condition searches for a file. Specify the name of the file or folder by using the FileOrFolderName parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **KeyName**

Specifies the registry key name for which to search. Use the format key\subkey.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **LdapFilter**

Specifies a Lightweight Directory Access Protocol (LDAP) filter to refine the results from the AD DS query to assess compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **LdapPrefix**

Specifies a valid LDAP prefix for the AD DS query that assesses compliance on client computers. This prefix can be either LDAP:// or GC://.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MetabasePath**

Specifies the path to the metabase file for Internet Information Services (IIS).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specifies the name of an IIS metabase file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Namespace**

Specifies a namespace from a WMI repository. The default value is Root\cimv2.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OmaUri**

Specifies a Uniform Resource Indicator (URI) that points to device-specific parameters for an Open Mobile Alliance (OMA) device.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Path**

Specifies the path for an OMA URI.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Property**

Specifies the property of the AD DS object used to assess compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PropertyId**

Specifies the property of AD DS that Configuration Manager uses to determine client compliance.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RegistryHive**

Specifies the root key in the registry that identifies the registry hive that you search. WMI uses the registry hive to return, set, and change the values of registry keys. The acceptable values for this parameter are:


* ClassesRoot


* CurrentConfig


* CurrentUser


* LocalMachine


* Users



Valid Values:

* ClassesRoot
* CurrentConfig
* CurrentUser
* LocalMachine
* Users






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[RegistryRootKey]`|true    |named   |False        |



#### **ScriptLanguage**

Specifies a scripting language to use. The acceptable values for this parameter are:


* PowerShell


* VBScript


* JScript



Valid Values:

* PowerShell
* VBScript
* JScript
* ShellScript






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[ScriptingLanguage]`|true    |named   |False        |



#### **SearchScope**

Specifies the search scope in AD DS. The acceptable values for this parameter are: Base, OneLevel, and Subtree.



Valid Values:

* Base
* OneLevel
* Subtree






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SearchScope]`|true    |named   |False        |



#### **Use32BitHost**

Indicates that the file or folder is associated with a 64-bit application.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseLoggedOnUserCredential**

Indicates whether to use logged on user credentials.






|Type       |Required|Position|PipelineInput|Aliases                   |
|-----------|--------|--------|-------------|--------------------------|
|`[Boolean]`|false   |named   |False        |UseLoggedOnUserCredentials|



#### **ValueName**

Specifies the value to be contained in the specified registry key.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **WhereClause**

Specifies a WQL query WHERE clause to apply to the specified namespace, class, and property on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **XmlFilePath**

Specifies a file that contains the XML query to use to assess compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **XmlNamespace**

Specifies an array of valid, full XML path language (XPath) queries to use to assess compliance on client computers.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |XmlNamespaces|



#### **XPathQuery**

Specifies a XPath query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
* IResultObject#SMS_GlobalCondition






---


### Notes




---


### Syntax
```PowerShell
New-CMGlobalCondition -AllInstances -Column <String> -Database <String> -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -AssemblyName <String> [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -Class <String> -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Namespace <String>] -Property <String> [-WhereClause <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -Column <String> -Database <String> -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} -DefaultInstance [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -Column <String> -Database <String> -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] -InstanceName <String> -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] -DistinguishedName <String> [-ForceWildcardHandling] -LdapFilter <String> [-LdapPrefix <String>] -Name <String> -Property <String> -SearchScope {Base | OneLevel | Subtree} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] [-ForceWildcardHandling] [-MetabasePath <String>] -Name <String> -PropertyId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] [-ForceWildcardHandling] [-Is64Bit <Boolean>] -KeyName <String> -Name <String> -RegistryHive {ClassesRoot | CurrentConfig | CurrentUser | LocalMachine | Users} -ValueName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] -Name <String> -ScriptLanguage {PowerShell | VBScript | JScript | ShellScript} [-Use32BitHost <Boolean>] [-UseLoggedOnUserCredential <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> [-XmlNamespace <String[]>] -XPathQuery <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> -XmlFilePath <String> [-XmlNamespace <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean | StringArray | IntegerArray | Base64 | Xml} [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -OmaUri <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] -FileOrFolderName <String> [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] [-IsFolder] -Name <String> -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMGlobalCondition [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] [-ForceWildcardHandling] [-Is64Bit <Boolean>] -KeyName <String> -Name <String> -RegistryHive {ClassesRoot | CurrentConfig | CurrentUser | LocalMachine | Users} [-Confirm] [-WhatIf] [<CommonParameters>]
```
