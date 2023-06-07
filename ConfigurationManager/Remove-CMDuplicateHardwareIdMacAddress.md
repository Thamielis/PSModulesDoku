Remove-CMDuplicateHardwareIdMacAddress
--------------------------------------




### Synopsis
Remove duplicate hardware identifiers by MAC address.



---


### Description

Use this cmdlet to remove duplicate hardware identifiers by MAC address. Configuration Manager ignores these MAC addresses for PXE boot and client registration. For more information, see Manage duplicate hardware identifiers (/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers).



>[!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDuplicateHardwareIdMacAddress](Get-CMDuplicateHardwareIdMacAddress)



* [New-CMDuplicateHardwareIdMacAddress](New-CMDuplicateHardwareIdMacAddress)



* [Remove-CMDuplicateHardwareIdGuid](Remove-CMDuplicateHardwareIdGuid)



* [Manage duplicate hardware identifiers](Manage duplicate hardware identifiers)





---


### Examples
#### Example 1: Specify an explicit MAC to remove
```PowerShell
Remove-CMDuplicateHardwareIdMacAddress -MacAddress '01:02:03:04:05:E0'
```

#### Example 2: Remove an ID for an input object
```PowerShell
$myMacAddress ='01:02:03:04:05:E0'
Remove-CMDuplicateHardwareIdMacAddress -InputObject $myMacAddress
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an object for the hardware identifier to remove from the site. This object is of type `IResultObject#SMS_CommonMacAddresses`. It also accepts string values.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Id     |



#### **MacAddress**

Specify a network MAC address of the hardware identifier to remove from the site. It's a colon-delimited (`:`) string value, for example `'01:02:03:04:05:E0'`.






|Type      |Required|Position|PipelineInput|Aliases                            |
|----------|--------|--------|-------------|-----------------------------------|
|`[String]`|true    |named   |False        |DuplicateID<br/>DuplicateHardwareId|



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
Remove-CMDuplicateHardwareIdMacAddress [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDuplicateHardwareIdMacAddress [-DisableWildcardHandling] [-ForceWildcardHandling] -MacAddress <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
