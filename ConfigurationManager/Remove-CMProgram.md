Remove-CMProgram
----------------




### Synopsis
Remove a program from a package.



---


### Description

Use this cmdlet to remove a program from a package. When you remove a program from a package, Configuration Manager removes all of the deployments for this program. If Configuration Manager has already run the deployed program on clients, Configuration Manager doesn't remove the software.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMProgram](Disable-CMProgram)



* [Enable-CMProgram](Enable-CMProgram)



* [Get-CMProgram](Get-CMProgram)



* [New-CMProgram](New-CMProgram)



* [Set-CMProgram](Set-CMProgram)





---


### Examples
#### Example 1: Remove a program by using a name and an ID
```PowerShell
Remove-CMProgram -PackageId "XYZ0000F" -ProgramName "ProgramD02"
```

#### Example 2: Remove a program by using an object variable
```PowerShell
$Prog = Get-CMProgram -Name "ProgramD02" -PackageId "XYZ0000F"
Remove-CMProgram -InputObject $Prog -Force
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a program object to remove. To get this object, use the Get-CMProgram (Get-CMProgram.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **PackageId**

Specify the ID of the package with the program to remove.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ProgramName**

Specify the name of the package with the program to remove.






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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMProgram [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMProgram [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -PackageId <String> -ProgramName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
