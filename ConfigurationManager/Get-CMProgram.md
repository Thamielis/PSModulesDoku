Get-CMProgram
-------------




### Synopsis
Get a program of a package.



---


### Description

Use this cmdlet to get a program of a package. Programs identify the actions that occur when the client receives the client package. You can associate multiple programs with the same package. For more information, see Packages and programs in Configuration Manager (/mem/configmgr/apps/deploy-use/packages-and-programs).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMProgram](Enable-CMProgram)



* [Disable-CMProgram](Disable-CMProgram)



* [New-CMProgram](New-CMProgram)



* [Remove-CMProgram](Remove-CMProgram)



* [Set-CMProgram](Set-CMProgram)



* [Packages and programs in Configuration Manager](Packages and programs in Configuration Manager)





---


### Examples
#### Example 1: Get a program by using a name and an ID
```PowerShell
Get-CMProgram -PackageId "XYZ0000F" -ProgramName "Script"
```



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



#### **Package**

Specify a package object with the program to get. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **PackageId**

Specify the ID of the package with the program to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageName**

Specify the name of the package with the program to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ProgramName**

Specify the name of the program in the package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_Program


* IResultObject#SMS_Program






---


### Notes
For more information on this return object and its properties, see SMS_Program server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_program-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMProgram [-DisableWildcardHandling] [-ForceWildcardHandling] -Package <IResultObject> [-ProgramName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMProgram [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageId <String> [-ProgramName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMProgram [-DisableWildcardHandling] [-ForceWildcardHandling] [-PackageName <String>] [-ProgramName <String>] [<CommonParameters>]
```
