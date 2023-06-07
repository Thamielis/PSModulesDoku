Undo-CMSoftwareInventory
------------------------




### Synopsis
Stops collecting software inventory data on files.



---


### Description

The Undo-CMSoftwareInventory cmdlet stops collecting information about files that are contained on client devices.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareInventory](Get-CMSoftwareInventory)



* [Set-CMSoftwareInventory](Set-CMSoftwareInventory)





---


### Examples
#### Example 1: Stop collecting software inventory data on a file
```PowerShell
PS XYZ:\>Undo-CMSoftwareInventory -Name "MSXML 6.0 Parser"
```
This command stops collecting software inventory data on the file named MSXML 6.0 Parser.


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



#### **Id**

Specifies an array of IDs of software files.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |SoftwareKey|



#### **Name**

Specifies an array of names of software files.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |CommonName|



#### **SoftwareInventory**

Specifies a CMSoftwareInventory object. To obtain a CMSoftwareInventory object, use the Get-CMSoftwareInventory (Get-CMSoftwareInventory.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |named   |True (ByValue)|InputObject|



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
Undo-CMSoftwareInventory [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Undo-CMSoftwareInventory [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Undo-CMSoftwareInventory [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareInventory <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
