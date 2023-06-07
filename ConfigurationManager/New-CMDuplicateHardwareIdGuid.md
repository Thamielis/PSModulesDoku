New-CMDuplicateHardwareIdGuid
-----------------------------




### Synopsis
Add duplicate hardware identifiers by GUID.



---


### Description

Use this cmdlet to add duplicate hardware identifiers by GUID. Configuration Manager ignores these GUIDs for PXE boot and client registration. For more information, see Manage duplicate hardware identifiers (/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers).



>[!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDuplicateHardwareIdGuid](Get-CMDuplicateHardwareIdGuid)



* [Remove-CMDuplicateHardwareIdGuid](Remove-CMDuplicateHardwareIdGuid)



* [New-CMDuplicateHardwareIdMacAddress](New-CMDuplicateHardwareIdMacAddress)



* [Manage duplicate hardware identifiers](Manage duplicate hardware identifiers)





---


### Examples
#### Example 1: Add a duplicate hardware entry for a GUID
```PowerShell
New-CMDuplicateHardwareIdGuid -Id 24D0F753-B2E2-4D9C-B07C-099C4FC1EF3C
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



#### **Id**

Specify the hardware GUID, for example, `feff51c2-9266-4da7-adec-4252c56a1713`.






|Type    |Required|Position|PipelineInput|Aliases                            |
|--------|--------|--------|-------------|-----------------------------------|
|`[Guid]`|true    |named   |False        |DuplicateId<br/>DuplicateHardwareId|



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
* IResultObject#SMS_CommonSmbiosGuids






---


### Notes
This cmdlet returns the SMS_CommonSmbiosGuids WMI class object.



---


### Syntax
```PowerShell
New-CMDuplicateHardwareIdGuid [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Guid> [-Confirm] [-WhatIf] [<CommonParameters>]
```
