Remove-CMDeviceAffinityFromUser
-------------------------------




### Synopsis
Removes device affinity from a Configuration Manager user.



---


### Description

The Remove-CMDeviceAffinityFromUser cmdlet removes device affinity from a user of Configuration Manager.



Device affinity in Configuration Manager associates a user with one or more devices. Instead of deploying applications to all the devices of a user, you deploy the application to the user and Configuration Manager automatically installs the application on all devices that are associated with that user. Device affinity removes the need for Configuration Manager to determine the names of all the devices of a user before you deploy applications for that user.



For more information about user device affinity, see How to Manage User Device Affinity in Configuration Manager (/mem/configmgr/apps/deploy-use/link-users-and-devices-with-user-device-affinity).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeviceAffinityToUser](Add-CMDeviceAffinityToUser)



* [Approve-CMUserDeviceAffinityRequest](Approve-CMUserDeviceAffinityRequest)



* [Deny-CMUserDeviceAffinityRequest](Deny-CMUserDeviceAffinityRequest)



* [Get-CMUserDeviceAffinity](Get-CMUserDeviceAffinity)



* [Get-CMUserDeviceAffinityRequest](Get-CMUserDeviceAffinityRequest)



* [Import-CMUserDeviceAffinity](Import-CMUserDeviceAffinity)





---


### Examples
#### Example 1: Remove device affinity from a user by user ID
```PowerShell
PS XYZ:\> Remove-CMDeviceAffinityFromUser -UserName "Patti Fuller" -DeviceName "WestDivUpdates05"
```
This command adds affinity to the device named WestDivUpdates05 for the user named Patti Fuller.


---


### Parameters
#### **DeviceId**

Specifies a device by using an ID.






|Type       |Required|Position|PipelineInput|Aliases  |
|-----------|--------|--------|-------------|---------|
|`[Int32[]]`|false   |named   |False        |DeviceIds|



#### **DeviceName**

Specifies a device by using a name.






|Type        |Required|Position|PipelineInput|Aliases    |
|------------|--------|--------|-------------|-----------|
|`[String[]]`|false   |named   |False        |DeviceNames|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UserId**

Specifies a user by using an ID.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **UserName**

Specifies an array of user names.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|true    |named   |False        |UniqueUserName|



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMDeviceAffinityFromUser [-DeviceId <Int32[]>] [-DeviceName <String[]>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -UserId <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeviceAffinityFromUser [-DeviceId <Int32[]>] [-DeviceName <String[]>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -UserName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
