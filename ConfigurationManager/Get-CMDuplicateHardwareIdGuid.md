Get-CMDuplicateHardwareIdGuid
-----------------------------




### Synopsis
View duplicate hardware identifiers by GUID.



---


### Description

Use this cmdlet to view duplicate hardware identifiers by GUID. Configuration Manager ignores these GUIDs for PXE boot and client registration. For more information, see Manage duplicate hardware identifiers (/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers).



>[!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDuplicateHardwareIdGuid](New-CMDuplicateHardwareIdGuid)



* [Remove-CMDuplicateHardwareIdGuid](Remove-CMDuplicateHardwareIdGuid)



* [Get-CMDuplicateHardwareIdMacAddress](Get-CMDuplicateHardwareIdMacAddress)



* [Manage duplicate hardware identifiers](Manage duplicate hardware identifiers)





---


### Examples
#### Example 1: View all GUIDs
```PowerShell
Get-CMDuplicateHardwareIdGuid | Select-Object SMBIOS_GUID
```

#### Example 2: Test for a specific GUID
```PowerShell
$guid = "AB83D231-8C12-9413-FEBA-C0F9888B9290"

if ( Get-CMDuplicateHardwareIdGuid -Id $guid ) {
  Write-Host $guid "exists in the site"
} else {
  Write-Host $guid "doesn't exist!"
}
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

Specify a duplicate hardware ID. The format of this value is a standard GUID, for example, `"feff51c2-9266-4da7-adec-4252c56a1713"`.






|Type      |Required|Position|PipelineInput|Aliases                            |
|----------|--------|--------|-------------|-----------------------------------|
|`[String]`|true    |named   |False        |DuplicateId<br/>DuplicateHardwareId|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_CommonSmbiosGuids


* IResultObject#SMS_CommonSmbiosGuids






---


### Notes
This cmdlet returns the SMS_CommonSmbiosGuids WMI class object.



---


### Syntax
```PowerShell
Get-CMDuplicateHardwareIdGuid [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
