New-CMGlobalConditionFile
-------------------------




### Synopsis
Creates a File System type global condition in Configuration Manager.



---


### Description

The New-CMGlobalConditionFile cmdlet creates a File System type global condition in Configuration Manager.



A global condition is a setting or expression in Configuration Manager that you can use to specify how Configuration Manager provides and deploys an application to clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMGlobalConditionFile](Set-CMGlobalConditionFile)



* [New-CMGlobalCondition](New-CMGlobalCondition)



* [New-CMGlobalConditionActiveDirectoryQuery](New-CMGlobalConditionActiveDirectoryQuery)



* [New-CMGlobalConditionAssembly](New-CMGlobalConditionAssembly)



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
$GlobalFloder = New-CMGlobalConditionFile -Path c:\ -FileOrFolderName test -IsFolder $true -Name Folder
```
This command creates a File System type folder global condition in Configuration Manager.
#### Example 1
```PowerShell
$GlobalFile = New-CMGlobalConditionFile -FilePath c:\test  -Name file
```
This command creates a File System type file global condition in Configuration Manager.


---


### Parameters
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



#### **FileOrFolderName**

Specifies the name of the file or folder object that will be searched for. You can specify system environment variables and the %USERPROFILE% environment variable in the file or folder name. You can also use the * and ? wildcards in the file name.






|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[String]`|true    |named   |False        |FileName<br/>FolderName|



#### **FilePath**

Specifies the path to the specified file on client computers. You can specify system environment variables and the %USERPROFILE% environment variable in the path.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Indicates whether the 64-bit system file location (%windir%\system32) should be searched in addition to the 32-bit system file location (%windir%\syswow64) on Configuration Manager clients that run a 64-bit version of Windows.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsFolder**

Indicate whether it is a folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specifies a name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Path**

Specifies the path to the specified  folder on client computers. You can specify system environment variables and the %USERPROFILE% environment variable in the path.






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
New-CMGlobalConditionFile [-Description <String>] [-DisableWildcardHandling] -FileOrFolderName <String> [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] [-IsFolder] -Name <String> -Path <String> [<CommonParameters>]
```
```PowerShell
New-CMGlobalConditionFile [-Description <String>] [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] [-IncludeSubfolder <Boolean>] [-Is64Bit <Boolean>] -Name <String> [<CommonParameters>]
```
