Get-CMSoftwareInventory
-----------------------




### Synopsis
Retrieves an object that collects software inventory data in Configuration Manager.



---


### Description

The Get-CMSoftwareInventory cmdlet retrieves an object that collects information about files that client devices contain.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMSoftwareInventory](Set-CMSoftwareInventory)



* [Undo-CMSoftwareInventory](Undo-CMSoftwareInventory)





---


### Examples
#### Example 1: Get a software inventory object
```PowerShell
PS XYZ:\> Get-CMSoftwareInventory -Name "MSXML 6.0 Parser"
```
This command gets the software inventory object named MSXML 6.0 Parser.


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
|`[String]`|false   |named   |False        |CommonName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_AISoftwareList


* IResultObject#SMS_AISoftwareList






---


### Notes




---


### Syntax
```PowerShell
Get-CMSoftwareInventory [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareInventory [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
