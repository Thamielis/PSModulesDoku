Set-CMGlobalConditionFile
-------------------------




### Synopsis
Sets a File System type global condition in Configuration Manager.



---


### Description

The Set-CMGlobalConditionFile cmdlet modifies settings for a File System type global condition in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMGlobalConditionFile](New-CMGlobalConditionFile)



* [Set-CMGlobalCondition](Set-CMGlobalCondition)



* [Set-CMGlobalConditionActiveDirectoryQuery](Set-CMGlobalConditionActiveDirectoryQuery)



* [Set-CMGlobalConditionAssembly](Set-CMGlobalConditionAssembly)



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
#### Example 1
```PowerShell
PS XYZ:\> $GlobalFloder = Set-CMGlobalConditionFile -Path c:\ -FileOrFolderName test -IsFolder $true -Name Floder
```
This command sets a File System type folder global condition in Configuration Manager.
#### Example 1
```PowerShell
PS XYZ:\> $GlobalFile = Set-CMGlobalConditionFile -FilePath c:\test  -Name file
```
This command sets a File System type file global condition in Configuration Manager.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileOrFolderName**

Specifies the name of the file or folder object that will be searched for. You can specify system environment variables and the %USERPROFILE% environment variable in the file or folder name. You can also use the * and ? wildcards in the file name.






|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[String]`|false   |named   |False        |FileName<br/>FolderName|



#### **FilePath**

Specifies the path to the specified file or folder on client computers. You can specify system environment variables and the %USERPROFILE% environment variable in the path.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IncludeSubfolder**

Indicates whether you also want to search any subfolders under the specified path.






|Type       |Required|Position|PipelineInput|Aliases          |
|-----------|--------|--------|-------------|-----------------|
|`[Boolean]`|false   |named   |False        |IncludeSubfolders|



#### **Is64Bit**

Indicates whether the 64-bit system file location (%windir%\system32) should be searched in addition to the 32-bit system file location (%windir%\syswow64) on Configuration Manager clients that run a 64-bit version of Windows.






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



#### **Path**

Specifies the path to the specified file or folder on client computers. You can specify system environment variables and the %USERPROFILE% environment variable in the path.






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
Set-CMGlobalConditionFile [-DisableWildcardHandling] [-FileOrFolderName <String>] [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> [-PassThru] [-Path <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMGlobalConditionFile [-DisableWildcardHandling] [-FilePath <String>] [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
