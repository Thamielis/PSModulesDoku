New-CMPackage
-------------




### Synopsis
Creates a Configuration Manager package.



---


### Description

The New-CMPackage cmdlet creates a Configuration Manager package. A package is a Configuration Manager object that contains the content files and instructions for distributing programs, software updates, boot images, operating system images, and drivers to Configuration Manager clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMPackage](Export-CMPackage)



* [Get-CMPackage](Get-CMPackage)



* [Import-CMPackage](Import-CMPackage)



* [Remove-CMPackage](Remove-CMPackage)



* [Set-CMPackage](Set-CMPackage)





---


### Examples
#### Example 1: Create a package
```PowerShell
PS XYZ:\> New-CMPackage -Name "ScriptsPackage01"
```
This command creates a Configuration Manager package named ScriptsPackage01.
#### Example 2: Create a package and add a description
```PowerShell
PS XYZ:\> New-CMPackage -Name "ScriptsPackage02" -Description "This package deploys scripts that run on a recurring schedule."
```
This command creates a Configuration Manager package named ScriptsPackage02 and adds the specified description to the package.


---


### Parameters
#### **Description**

Specifies a description for the package. You can use a maximum of 128 characters.






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



#### **FromDefinition**

Indicates that Configuration Manager creates the package from a package definition file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **Language**

Specifies the language version of the package. You can use a maximum of 32 characters in a format that you choose to use to identify the language version. Configuration Manager uses the Language parameter together with Manufacturer , Name , and Version to identify a package. For example, you can have an English version and a German version of the same package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Manufacturer**

Specifies a manufacturer name to help you identify the package. You can use a maximum of 32 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specifies a name for the package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageDefinitionName**

Specifies the name of a package definition file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageNoSourceFile**

Indicates that the package does not require source files to be present on client devices.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **PackagePath**

Specifies a share name or path that Configuration Manager creates for the package source files on distribution points.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Path**

Specifies the location of the files to add to the package.


You can specify either a full local path or a UNC path. Make sure that this location contains all the files and subdirectories that the program needs to complete, including any scripts.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|false   |named   |False        |PackageSourcePath|



#### **SourceFileType**

Specifies the source file type. The acceptable values for this parameter are:


* AlwaysObtainSourceFile


* CreateCompressedVersionOfSourceFile



Valid Values:

* AlwaysObtainSourceFile
* CreateCompressedVersionOfSourceFile






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[SourceFileType]`|true    |named   |False        |



#### **SourceFolderPath**

Specifies the location of the source files for the package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SourceFolderPathType**

Specifies the source folder path type. The acceptable values for this parameter are:


* LocalFolderOnSiteServer


* UncNetworkPath



Valid Values:

* UncNetworkPath
* LocalFolderOnSiteServer






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[SourceFolderPathType]`|true    |named   |False        |



#### **Version**

Specifies a version number for the package.






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
* IResultObject#SMS_Package






---


### Notes




---


### Syntax
```PowerShell
New-CMPackage [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Language <String>] [-Manufacturer <String>] -Name <String> [-Path <String>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackage [-DisableWildcardHandling] [-ForceWildcardHandling] -FromDefinition -PackageDefinitionName <String> -PackageNoSourceFile [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackage [-DisableWildcardHandling] [-ForceWildcardHandling] -FromDefinition -PackageNoSourceFile -PackagePath <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackage [-DisableWildcardHandling] [-ForceWildcardHandling] -FromDefinition -PackageDefinitionName <String> -SourceFileType {AlwaysObtainSourceFile | CreateCompressedVersionOfSourceFile} -SourceFolderPath <String> -SourceFolderPathType {UncNetworkPath | LocalFolderOnSiteServer} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackage [-DisableWildcardHandling] [-ForceWildcardHandling] -FromDefinition -PackagePath <String> -SourceFileType {AlwaysObtainSourceFile | CreateCompressedVersionOfSourceFile} -SourceFolderPath <String> -SourceFolderPathType {UncNetworkPath | LocalFolderOnSiteServer} [-Confirm] [-WhatIf] [<CommonParameters>]
```
