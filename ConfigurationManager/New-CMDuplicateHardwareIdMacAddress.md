New-CMDuplicateHardwareIdMacAddress
-----------------------------------




### Synopsis
Add duplicate hardware identifiers by MAC address.



---


### Description

Use this cmdlet to add duplicate hardware identifiers by MAC address. Configuration Manager ignores these MAC addresses for PXE boot and client registration. For more information, see Manage duplicate hardware identifiers (/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers).



>[!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDuplicateHardwareIdMacAddress](Get-CMDuplicateHardwareIdMacAddress)



* [Remove-CMDuplicateHardwareIdMacAddress](Remove-CMDuplicateHardwareIdMacAddress)



* [New-CMDuplicateHardwareIdGuid](New-CMDuplicateHardwareIdGuid)



* [Manage duplicate hardware identifiers](Manage duplicate hardware identifiers)





---


### Examples
#### Example 1: Add a duplicate hardware entry for a MAC address
```PowerShell
New-CMDuplicateHardwareIdMacAddress -MacAddress '01:02:03:04:05:E0'
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



#### **MacAddress**

Specify the MAC address of the machine as a string with colon (`:`) delimiters. For example, `'01:02:03:04:05:E0'`






|Type      |Required|Position|PipelineInput|Aliases                            |
|----------|--------|--------|-------------|-----------------------------------|
|`[String]`|true    |named   |False        |DuplicateId<br/>DuplicateHardwareId|



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
* IResultObject#SMS_CommonMacAddresses






---


### Notes
This cmdlet returns the SMS_CommonMacAddresses WMI class object.



---


### Syntax
```PowerShell
New-CMDuplicateHardwareIdMacAddress [-DisableWildcardHandling] [-ForceWildcardHandling] -MacAddress <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
