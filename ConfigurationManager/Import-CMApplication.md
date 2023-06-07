Import-CMApplication
--------------------




### Synopsis
Imports an application into Configuration Manager.



---


### Description

The Import-CMApplication cmdlet imports a package created by the Export-CMApplication (Export-CMApplication.md)cmdlet. A package contains one or more applications and related objects, such as catalogs. If the package contains content, the application package imports the content, or includes a reference to the content.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [ConvertFrom-CMApplication](ConvertFrom-CMApplication)



* [ConvertTo-CMApplication](ConvertTo-CMApplication)



* [Export-CMApplication](Export-CMApplication)



* [Get-CMApplication](Get-CMApplication)



* [New-CMApplication](New-CMApplication)



* [Remove-CMApplication](Remove-CMApplication)



* [Resume-CMApplication](Resume-CMApplication)



* [Set-CMApplication](Set-CMApplication)



* [Suspend-CMApplication](Suspend-CMApplication)





---


### Examples
#### Example 1: Import an application
```PowerShell
PS XYZ:\>Import-CMApplication -FilePath "\\Server1\resource\test.zip" -ImportActionType DirectImport
```
This command imports the application stored in test.zip, including the application objects.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FilePath**

Specifies a file path for the application.






|Type      |Required|Position|PipelineInput|Aliases                             |
|----------|--------|--------|-------------|------------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>ImportFilePath<br/>Path|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ImportActionType**

Specifies an import action type for the application. If this application already exists in the Software Library, Configuration Manager adds a revision to the existing application unless you modify the action to create a new application. Valid values are:


* Skip. This option is not supported. - NotSet. No action is specified. The default behavior is:     - If there is a conflict with the application model ID, a new revision is added to the existing application.     - If there is a conflict with the application name, a new application is created with a new name. - DirectImport. Imports the application objects. The default behavior is:     - If there is a conflict with the application model ID, the error is displayed.     - If there is a conflict with the application name, a new application is created with a new name. - Rename. This option is not supported. - Overwrite. Maps objects despite name or scope duplication. If the revision of the application does not match the revision of the application to import, then a new revision is added to the existing application. - ImportFail. This option is not supported.



Valid Values:

* NotSet
* Skip
* DirectImport
* Rename
* Overwrite
* ImportFail






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[ImportActionType]`|false   |named   |False        |



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
Import-CMApplication [-DisableWildcardHandling] -FilePath <String> [-ForceWildcardHandling] [-ImportActionType {NotSet | Skip | DirectImport | Rename | Overwrite | ImportFail}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
