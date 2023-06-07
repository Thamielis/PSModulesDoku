Enable-CMProgram
----------------




### Synopsis
Enable a program in a package.



---


### Description

Use this cmdlet to enable a program in a package. You can enable a program to resume availability of it to clients.



For more information, see Packages and programs in Configuration Manager (/mem/configmgr/apps/deploy-use/packages-and-programs).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMProgram](Disable-CMProgram)



* [Get-CMProgram](Get-CMProgram)



* [New-CMProgram](New-CMProgram)



* [Remove-CMProgram](Remove-CMProgram)



* [Set-CMProgram](Set-CMProgram)



* [Get-CMPackage](Get-CMPackage)





---


### Examples
#### Example 1: Enable a program
```PowerShell
Enable-CMProgram -PackageId "XYZ00007" -ProgramName "ProgramD02"
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



#### **InputObject**

Specify a program object to enable. To get this object, use the Get-CMProgram (Get-CMProgram.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Program|



#### **PackageId**

Specify the ID of the package with the program to enable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageName**

Specify the name of the package with the program to enable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ProgramName**

Specify the name of the package with the program to enable.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* 






---


### Notes




---


### Syntax
```PowerShell
Enable-CMProgram [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Enable-CMProgram [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageId <String> [-PassThru] -ProgramName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Enable-CMProgram [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageName <String> [-PassThru] -ProgramName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
