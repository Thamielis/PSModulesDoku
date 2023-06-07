Set-CMGlobalCondition
---------------------




### Synopsis
Modifies settings for a Configuration Manager global condition.



---


### Description

The Set-CMGlobalCondition cmdlet modifies settings for a global condition. You can add or remove a security scope for a global condition. You can specify a global condition by name or ID, or use the Get-CMGlobalCondition cmdlet to obtain a global condition object.



Configuration Manager uses global conditions to represent business or technical conditions. Global conditions specify how to provide and deploy applications to client devices.



Each global condition must have at least one security scope.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMGlobalCondition](New-CMGlobalCondition)



* [Get-CMGlobalCondition](Get-CMGlobalCondition)



* [Remove-CMGlobalCondition](Remove-CMGlobalCondition)



* [Set-CMGlobalCondition](Set-CMGlobalCondition)



* [Set-CMGlobalConditionAssembly](Set-CMGlobalConditionAssembly)



* [Set-CMGlobalConditionFile](Set-CMGlobalConditionFile)



* [Set-CMGlobalConditionIisMetabase](Set-CMGlobalConditionIisMetabase)



* [Set-CMGlobalConditionOmaUri](Set-CMGlobalConditionOmaUri)



* [Set-CMGlobalConditionRegistryKey](Set-CMGlobalConditionRegistryKey)



* [Set-CMGlobalConditionRegistryValue](Set-CMGlobalConditionRegistryValue)



* [Set-CMGlobalConditionScript](Set-CMGlobalConditionScript)



* [Set-CMGlobalConditionSqlQuery](Set-CMGlobalConditionSqlQuery)



* [Set-CMGlobalConditionWqlQuery](Set-CMGlobalConditionWqlQuery)



* [Set-CMGlobalConditionXPathQuery](Set-CMGlobalConditionXPathQuery)





---


### Examples
#### Example 1: Add a security scope
```PowerShell
PS XYZ:\> Set-CMGlobalCondition -Name "CPU speed" -SecurityScopeAction AddMembership -SecurityScopeName "Scope22"
```
This command adds the security scope named Scope22 to the global condition named CPU speed.
#### Example 2: Remove a security scope by using a variable
```PowerShell
PS XYZ:\> $CMGC = Get-CMGlobalCondition -Name "CPU speed"
PS XYZ:\> Set-CMGlobalCondition -InputObject $CMGC -SecurityScopeAction RemoveMembership -SecurityScopeName "Scope22"
```
The first command uses the Get-CMGlobalCondition cmdlet to get the global condition named CPU speed and store it in the $CMGC variable.


The second command removes the security scope named Scope22 from the global condition stored in the $CMGC variable.


---


### Parameters
#### **AssemblyName**

Specifies the name of an assembly for which to search. An assembly name must be registered in the global assembly cache.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Class**

Specifies a Windows Management Instrumentation (WMI) class used to build a WMI Query Language (WQL) query. The query assesses compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Column**

Specifies the column name used to assess the compliance of the global condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Database**

Specifies the name of a database. The SQL query runs on this database.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Description**

Specifies a description for the global condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistinguishedName**

Specifies the distinguished name of the Active Directory Domain Services (AD DS) object to assess for compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FileOrFolderName**

Specifies the name of a file or folder. Specify the IsFolder parameter to search for a folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FilePath**

Specifies a file path for the file that the condition assesses for compliance.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
|`[String]`|false   |named   |False        |



#### **Is64Bit**

Indicates that the global condition searches the 64-bit system file location in addition to the 32-bit system file location.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **KeyName**

Specifies the registry key name for which to search. Use the format key\subkey.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **LdapFilter**

Specifies a Lightweight Directory Access Protocol (LDAP) filter to refine the results from the AD DS query to assess compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **LdapPrefix**

Specifies a valid LDAP prefix for the AD DS query that assesses compliance on client computers. The acceptable values for this parameter are: LDAP:// or GC://.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MetabasePath**

Specifies the path to the metabase file for Internet Information Services (IIS).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specifies the name of the global conditions. This value corresponds to the LocalizedDisplayName property of a global condition object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Namespace**

Specifies a namespace from a WMI repository. The default value is Root\cimv2.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NewName**

Specifies a new name for the global condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OmaUri**

Specifies a Uniform Resource Indicator (URI) that points to device-specific parameters for an Open Mobile Alliance (OMA) device.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns the current working object. By default, this cmdlet does not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

Specifies the path for an OMA URI.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Property**

Specifies the property of the AD DS object used to assess compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PropertyId**

Specifies the property of AD DS that Configuration Manager uses to determine client compliance.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
|`[RegistryRootKey]`|false   |named   |False        |



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
|`[ScriptingLanguage]`|false   |named   |False        |



#### **SearchScope**

Specifies the search scope in AD DS. The acceptable values for this parameter are:


* Base


* OneLevel


* Subtree



Valid Values:

* Base
* OneLevel
* Subtree






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SearchScope]`|false   |named   |False        |



#### **Use32BitHost**

Indicates that the file or folder is associated with a 64-bit application.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseAllInstances**

Indicates that the global condition searches all database instances. To search a named instance, specify the InstanceName parameter. To search the default instance, specify the UseDefaultInstance parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UseDefaultInstance**

Indicates that the global condition searches the default database instance. To search a named instance, specify the InstanceName parameter. To search all instances, specify the UseAllInstances parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UseLoggedOnUserCredential**

Indicates whether to use logged on user credentials.






|Type       |Required|Position|PipelineInput|Aliases                   |
|-----------|--------|--------|-------------|--------------------------|
|`[Boolean]`|false   |named   |False        |UseLoggedOnUserCredentials|



#### **ValueName**

Specifies the value to be contained in the specified registry key.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **WhereClause**

Specifies a WQL query WHERE clause to apply to the specified namespace, class, and property on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **XmlFilePath**

Specifies a file that contains the XML query to use to assess compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **XmlNamespace**

Specifies an array of valid, full XML path language (XPath) queries to use to assess compliance on client computers.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |XmlNamespaces|



#### **XPathQuery**

Specifies a XPath query.






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
Set-CMGlobalCondition [-AssemblyName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-Class <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Namespace <String>] [-PassThru] [-Property <String>] [-WhereClause <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-Column <String>] [-Database <String>] [-DisableWildcardHandling] [-FilePath <String>] [-ForceWildcardHandling] -Name <String> [-PassThru] [-UseDefaultInstance] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-Column <String>] [-Database <String>] [-DisableWildcardHandling] [-FilePath <String>] [-ForceWildcardHandling] -Name <String> [-PassThru] [-UseAllInstances] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-Column <String>] [-Database <String>] [-DisableWildcardHandling] [-FilePath <String>] [-ForceWildcardHandling] [-InstanceName <String>] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-DisableWildcardHandling] [-DistinguishedName <String>] [-ForceWildcardHandling] [-LdapFilter <String>] [-LdapPrefix <String>] -Name <String> [-PassThru] [-Property <String>] [-SearchScope {Base | OneLevel | Subtree}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-DisableWildcardHandling] [-FileOrFolderName <String>] [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> [-PassThru] [-Path <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-DisableWildcardHandling] [-FilePath <String>] [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-DisableWildcardHandling] [-FilePath <String>] [-ForceWildcardHandling] -Name <String> [-PassThru] [-ScriptLanguage {PowerShell | VBScript | JScript | ShellScript}] [-Use32BitHost <Boolean>] [-UseLoggedOnUserCredential <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-DisableWildcardHandling] [-FilePath <String>] [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> [-PassThru] [-XmlFilePath <String>] [-XmlNamespace <String[]>] [-XPathQuery <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-DisableWildcardHandling] [-ForceWildcardHandling] [-Is64Bit <Boolean>] [-KeyName <String>] -Name <String> [-PassThru] [-RegistryHive {ClassesRoot | CurrentConfig | CurrentUser | LocalMachine | Users}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-DisableWildcardHandling] [-ForceWildcardHandling] [-Is64Bit <Boolean>] [-KeyName <String>] -Name <String> [-PassThru] [-RegistryHive {ClassesRoot | CurrentConfig | CurrentUser | LocalMachine | Users}] [-ValueName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-DisableWildcardHandling] [-ForceWildcardHandling] [-MetabasePath <String>] -Name <String> [-PassThru] [-PropertyId <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalCondition [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -OmaUri <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
