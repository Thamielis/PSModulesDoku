New-CMInstallationSourceFile
----------------------------




### Synopsis
Creates an installation source file for Configuration Manager.



---


### Description

The New-CMInstallationSourceFile cmdlet creates an installation source file for Configuration Manager. An installation source file is an object that contains installation source parameters for a secondary site installation. A secondary site has no Configuration Manager database of its own. Instead, it forwards information that it gets from clients to a primary site that stores the data for all the secondary sites that are attached to it.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Create an installation source file
```PowerShell
PS XYZ:\> New-CMInstallationSourceFile -CopyFromParentSiteServer
```
This command creates an installation source file for a secondary site installation by copying the installation files from the primary site.


---


### Parameters
#### **CopyFromNetworkLocation**

Indicates that Configuration Manager copies the installation files for a secondary site installation from a specific Universal Naming Convention (UNC) path.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **CopyFromParentSiteServer**

Indicates that Configuration Manager copies the installation files for a secondary site installation from the primary site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **CopyFromSecondarySiteLocation**

Indicates that the installation files for a secondary site installation reside on the secondary site server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



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



#### **LocalPath**

Specifies a path to source files in the local file system of the secondary site server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **UncPath**

Specifies a UNC path to source files in the local file system of the secondary site server.






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
* IResultObject#SMS_EmbeddedProperty, IResultObject[]#SMS_EmbeddedProperty






---


### Notes




---


### Syntax
```PowerShell
New-CMInstallationSourceFile -CopyFromNetworkLocation [-DisableWildcardHandling] [-ForceWildcardHandling] -UncPath <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMInstallationSourceFile -CopyFromParentSiteServer [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMInstallationSourceFile -CopyFromSecondarySiteLocation [-DisableWildcardHandling] [-ForceWildcardHandling] -LocalPath <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
