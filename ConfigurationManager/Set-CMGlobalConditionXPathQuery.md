Set-CMGlobalConditionXPathQuery
-------------------------------




### Synopsis
Sets a XPath Query type global condition in Configuration Manager.



---


### Description

The Set-CMGlobalConditionXPathQuery cmdlet modifies settings for a XPath Query type global condition in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMGlobalConditionXPathQuery](New-CMGlobalConditionXPathQuery)



* [Set-CMGlobalCondition](Set-CMGlobalCondition)



* [Set-CMGlobalConditionActiveDirectoryQuery](Set-CMGlobalConditionActiveDirectoryQuery)



* [Set-CMGlobalConditionAssembly](Set-CMGlobalConditionAssembly)



* [Set-CMGlobalConditionFile](Set-CMGlobalConditionFile)



* [Set-CMGlobalConditionIisMetabase](Set-CMGlobalConditionIisMetabase)



* [Set-CMGlobalConditionOmaUri](Set-CMGlobalConditionOmaUri)



* [Set-CMGlobalConditionRegistryKey](Set-CMGlobalConditionRegistryKey)



* [Set-CMGlobalConditionRegistryValue](Set-CMGlobalConditionRegistryValue)



* [Set-CMGlobalConditionScript](Set-CMGlobalConditionScript)



* [Set-CMGlobalConditionSqlQuery](Set-CMGlobalConditionSqlQuery)



* [Set-CMGlobalConditionWqlQuery](Set-CMGlobalConditionWqlQuery)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $GlobalXpath = Set-CMGlobalConditionXPathQuery -DataType String -XmlFilePath "c:\A" -XPathQuery "/" -Name GC8
```
This command sets a XPath Query type global condition in Configuration Manager.


---


### Parameters
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

Indicates whether to search any sub-folders under the specified path.






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



#### **PassThru**

Returns the current working object. By default, this cmdlet does not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **XmlFilePath**

Specifies the path to the XML file on client computers that will be used to assess compliance. Configuration Manager supports the use of all Windows system environment variables and the %USERPROFILE% user variable in the path name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **XmlNamespace**

Specifies namespaces to use during the XPath query.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |XmlNamespaces|



#### **XPathQuery**

Specifies a valid full XML path language (XPath) query to use to assess compliance on client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **XPathQueryFilePath**

Specifies a XPath query file path.






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
Set-CMGlobalConditionXPathQuery [-DisableWildcardHandling] [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> [-PassThru] [-XmlFilePath <String>] [-XmlNamespace <String[]>] [-XPathQuery <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalConditionXPathQuery [-DisableWildcardHandling] [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> [-PassThru] [-XmlFilePath <String>] [-XmlNamespace <String[]>] [-XPathQueryFilePath <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
