Remove-CMHardwareRequirement
----------------------------




### Synopsis
Removes Configuration Manager hardware requirement objects for products.



---


### Description

The Remove-CMHardwareRequirement cmdlet removes hardware requirement objects from Configuration Manager.



Configuration Manager manages Asset Intelligence information, including hardware requirements, for different software products. You can add, modify, or delete your own hardware requirements, but you cannot change built-in hardware requirement objects.



You can use this cmdlet to remove hardware requirement objects. You can specify a product by name or obtain a requirement by using the Get-CMHardwareRequirement cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMHardwareRequirement](Get-CMHardwareRequirement)



* [New-CMHardwareRequirement](New-CMHardwareRequirement)



* [Set-CMHardwareRequirement](Set-CMHardwareRequirement)





---


### Examples
#### Example 1: Remove a hardware requirement
```PowerShell
PS XYZ:\> Remove-CMHardwareRequirement -Product "Accounts Program"
Remove
Are you sure you wish to remove HardwareRequirement: Product="Accounts Program"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```
This command removes the hardware requirement object for a product named Accounts Program.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Performs the action without a confirmation message.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a hardware requirement object. To obtain a hardware requirement object, use the Get-CMHardwareRequirement cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Product**

Specifies the name of a software product name.






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
Remove-CMHardwareRequirement [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMHardwareRequirement [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Product <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
