Remove-CMDuplicateHardwareIdGuid
--------------------------------




### Synopsis
Remove duplicate hardware identifiers by GUID.



---


### Description

Use this cmdlet to remove duplicate hardware identifiers by GUID. Configuration Manager ignores these GUIDs for PXE boot and client registration. For more information, see Manage duplicate hardware identifiers (/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers).



>[!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDuplicateHardwareIdGuid](Get-CMDuplicateHardwareIdGuid)



* [New-CMDuplicateHardwareIdGuid](New-CMDuplicateHardwareIdGuid)



* [Remove-CMDuplicateHardwareIdMacAddress](Remove-CMDuplicateHardwareIdMacAddress)



* [Manage duplicate hardware identifiers](Manage duplicate hardware identifiers)





---


### Examples
#### Example 1: Specify an explicit ID to remove
```PowerShell
Remove-CMDuplicateHardwareIdGuid -Id 24D0F753-B2E2-4D9C-B07C-099C4FC1EF3C
```

#### Example 2: Remove an ID for an input object
```PowerShell
$myGuid = [guid]"24D0F753-B2E2-4D9C-B07C-099C4FC1EF3C"

Remove-CMDuplicateHardwareIdGuid -InputObject $myGuid
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



#### **Id**

Specify the GUID of the hardware identifier to remove from the site. This value is a standard guide, for example `24D0F753-B2E2-4D9C-B07C-099C4FC1EF3C`.






|Type    |Required|Position|PipelineInput|Aliases                            |
|--------|--------|--------|-------------|-----------------------------------|
|`[Guid]`|true    |named   |False        |DuplicateId<br/>DuplicateHardwareId|



#### **InputObject**

Specify a GUID object for the hardware identifier to remove from the site. This object is of type `IResultObject#SMS_CommonSmbiosGuids`. It also accepts string and GUID type values.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



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
Remove-CMDuplicateHardwareIdGuid [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Guid> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDuplicateHardwareIdGuid [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
