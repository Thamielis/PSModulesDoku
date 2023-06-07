Set-CMHardwareRequirement
-------------------------




### Synopsis
Changes Configuration Manager hardware requirement settings for a product.



---


### Description

The Set-CMHardwareRequirement cmdlet changes settings for hardware requirements for software products.



Configuration Manager manages Asset Intelligence information, including hardware requirements, for different software products. You can add, modify, or delete your own hardware requirements, but you cannot change built-in hardware requirements.



You can use this cmdlet to modify the minimum requirements associated with a software product or change the name that Configuration Manager uses for a product. You can specify a product by name or obtain a product by using the Get-CMHardwareRequirement cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMHardwareRequirement](Get-CMHardwareRequirement)



* [New-CMHardwareRequirement](New-CMHardwareRequirement)



* [Remove-CMHardwareRequirement](Remove-CMHardwareRequirement)





---


### Examples
#### Example 1: Change minimum RAM value
```PowerShell
PS XYZ:\> Set-CMHardwareRequirement -Product "Accounts Program" -MinRam 161072
```
This command sets the minimum RAM value for a specified product.
#### Example 2: Change minimum disk size value for a hardware requirements object
```PowerShell
PS XYZ:\> $CMHR = Get-CMHardwareRequirement -Product "Accounts Program"
PS XYZ:\> Set-CMHardwareRequirement -InputObject $CMHR -MinDiskSize 1600000
```
The first command gets the hardware requirements object for Accounts Program and stores it in the $CMHR variable.


The second command changes the minimum disk size for the object stored in $CMHR.


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

Specifies a hardware requirement object. To obtain a hardware requirement object, use the Get-CMHardwareRequirement (Get-CMHardwareRequirement.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **MinCpu**

Specifies a minimum CPU speed, in megahertz (MHz), required for a software product.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MinDiskFree**

Specifies a minimum amount of available disk memory, in kilobytes (KB), required for a software product.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int64]`|false   |named   |False        |



#### **MinDiskSize**

Specifies a minimum disk size, in kilobytes, required for a software product.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int64]`|false   |named   |False        |



#### **MinRam**

Specifies a minimum amount of random access memory (RAM), in kilobytes, required for a software product.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int64]`|false   |named   |False        |



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
Set-CMHardwareRequirement [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-MinCpu <Int32>] [-MinDiskFree <Int64>] [-MinDiskSize <Int64>] [-MinRam <Int64>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMHardwareRequirement [-DisableWildcardHandling] [-ForceWildcardHandling] [-MinCpu <Int32>] [-MinDiskFree <Int64>] [-MinDiskSize <Int64>] [-MinRam <Int64>] -Product <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
