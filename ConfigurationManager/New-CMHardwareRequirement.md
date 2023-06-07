New-CMHardwareRequirement
-------------------------




### Synopsis
Creates a Configuration Manager hardware requirement object for a product.



---


### Description

The New-CMHardwareRequirement cmdlet creates a hardware requirement object for a product.



Configuration Manager manages Asset Intelligence information, including hardware requirements, for different software products. You can add, modify, or delete your own hardware requirements, but you cannot change built-in hardware requirement objects.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMHardwareRequirement](Get-CMHardwareRequirement)



* [Remove-CMHardwareRequirement](Remove-CMHardwareRequirement)



* [Set-CMHardwareRequirement](Set-CMHardwareRequirement)





---


### Examples
#### Example 1: Create a hardware requirement object
```PowerShell
PS XYZ:\> New-CMHardwareRequirement -MinCpu 233 -MinDiskFree 1572864 -MinDiskSize 10485760 -MinRam 131072 -Product "Accounts Program"


IsLocal     :
MinCPU      : 233
MinDiskFree : 1572864
MinDiskSize : 10485760
MinRAM      : 131072
Product     : Accounts Program
State       :
```
This command creates a hardware requirement object for a software product called Accounts Program. The command specifies the minimum hardware requirements for the product. If you do not include all of these required parameters, the system prompts you for values.


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



#### **MinCpu**

Specifies the minimum CPU speed, in megahertz (MHz), required for a software product.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **MinDiskFree**

Specifies the minimum amount of available disk memory, in kilobytes (KB), required for a software product.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int64]`|true    |named   |False        |



#### **MinDiskSize**

Specifies the minimum disk size, in kilobytes, required for a software product.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int64]`|true    |named   |False        |



#### **MinRam**

Specifies the minimum amount of random access memory (RAM), in kilobytes, required for a software product.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int64]`|true    |named   |False        |



#### **Product**

Specifies the name of a software product.






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
* IResultObject#SMS_AIHardwareRequirements






---


### Notes




---


### Syntax
```PowerShell
New-CMHardwareRequirement [-DisableWildcardHandling] [-ForceWildcardHandling] -MinCpu <Int32> -MinDiskFree <Int64> -MinDiskSize <Int64> -MinRam <Int64> -Product <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
