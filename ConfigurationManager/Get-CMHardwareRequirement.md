Get-CMHardwareRequirement
-------------------------




### Synopsis
Gets Configuration Manager hardware requirements for products.



---


### Description

The Get-CMHardwareRequirement cmdlet gets hardware requirements objects for software products.



Configuration Manager manages Asset Intelligence information, including hardware requirements, for different software products. You can add, modify, or delete your own hardware requirements, but you cannot change built-in hardware requirement objects.



You can use this cmdlet to get all the hardware requirement objects for a Configuration Manager server or one or more hardware requirement objects for a specified product names. You can use hardware requirements with other cmdlets, such as the Remove-CMHardwareRequirement cmdlet or the Set-CMHardwareRequirement cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMHardwareRequirement](New-CMHardwareRequirement)



* [Remove-CMHardwareRequirement](Remove-CMHardwareRequirement)



* [Set-CMHardwareRequirement](Set-CMHardwareRequirement)





---


### Examples
#### Example 1: Get a hardware requirement
```PowerShell
PS XYZ:\> Get-CMHardwareRequirement -Product "Accounts Program"
IsLocal     : False
MinCPU      : 233
MinDiskFree : 1572864
MinDiskSize : 10485760
MinRAM      : 131072
Product     : Accounts Program
State       : 0
```
This command gets the hardware requirement object for a product named Accounts Program.


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



#### **Product**

Specifies the name of a software product.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_AIHardwareRequirements


* IResultObject#SMS_AIHardwareRequirements






---


### Notes




---


### Syntax
```PowerShell
Get-CMHardwareRequirement [-DisableWildcardHandling] [-ForceWildcardHandling] [-Product <String>] [<CommonParameters>]
```
