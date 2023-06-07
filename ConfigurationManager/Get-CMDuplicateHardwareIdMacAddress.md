Get-CMDuplicateHardwareIdMacAddress
-----------------------------------




### Synopsis
View duplicate hardware identifiers by MAC address.



---


### Description

Use this cmdlet to view duplicate hardware identifiers by network MAC address. Configuration Manager ignores these MAC addresses for PXE boot and client registration. For more information, see Manage duplicate hardware identifiers (/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers).



>[!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDuplicateHardwareIdMacAddress](New-CMDuplicateHardwareIdMacAddress)



* [Remove-CMDuplicateHardwareIdMacAddress](Remove-CMDuplicateHardwareIdMacAddress)



* [Get-CMDuplicateHardwareIdGuid](Get-CMDuplicateHardwareIdGuid)



* [Manage duplicate hardware identifiers](Manage duplicate hardware identifiers)





---


### Examples
#### Example 1: View all MAC addresses
```PowerShell
Get-CMDuplicateHardwareIdMacAddress | Select-Object MACAddress
```

#### Example 2: Test for a specific MAC address
```PowerShell
$mac = "01:23:45:67:89:AB"

if ( Get-CMDuplicateHardwareIdMacAddress -Id $mac ) {
  Write-Host $mac "exists in the site"
} else {
  Write-Host $mac "doesn't exist!"
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

Specify a duplicate hardware MAC address. The format of this value uses colon (`:`) delimiters, for example, `"01:23:45:67:89:AB"`.






|Type      |Required|Position|PipelineInput|Aliases                            |
|----------|--------|--------|-------------|-----------------------------------|
|`[String]`|true    |named   |False        |DuplicateId<br/>DuplicateHardwareId|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_CommonMacAddresses


* IResultObject#SMS_CommonMacAddresses






---


### Notes
This cmdlet returns the SMS_CommonMacAddresses WMI class object.



---


### Syntax
```PowerShell
Get-CMDuplicateHardwareIdMacAddress [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
