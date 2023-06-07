New-CMOneDriveBusinessProfile
-----------------------------




### Synopsis
Create a OneDrive for Business profile policy.



---


### Description

Create a OneDrive for Business profile policy. Use this policy to move Windows known folders to OneDrive for Business. These folders include Desktop, Documents, and Pictures. In each profile, you can specify settings for moving the Windows known folders. For more information on OneDrive for Business, see Redirect and move Windows known folders to OneDrive (/onedrive/redirect-known-folders).



For more information on this Configuration Manager policy, see OneDrive for Business profiles (/mem/configmgr/compliance/deploy-use/onedrive-profile).



---


### Related Links
* [Get-CMOneDriveBusinessProfile](Get-CMOneDriveBusinessProfile)



* [Set-CMOneDriveBusinessProfile](Set-CMOneDriveBusinessProfile)



* [OneDrive for Business profiles](OneDrive for Business profiles)





---


### Examples
#### Example 1
```PowerShell
$plats = Get-CMSupportedPlatform -Name "*Windows*10*" -Fast

New-CMOneDriveBusinessProfile -Name "ODfB policy" -SupportedPlatform $plats -O365TenantId "05d683b9-caed-4eea-b229-45f72b89ca05" -KnownFolderMoveOption SilentlyMove -ShowNotification $true -PreventRedirectKnownFolders $true
```



---


### Parameters
#### **Description**

Specify an optional description for the OneDrive for Business policy to better identify it.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



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



#### **KnownFolderMoveOption**

Specify how you want to move the known folders to OneDrive:


* `PromptToMove`: Prompt users to move Windows known folders to OneDrive. The user sees a wizard to move their files. If they choose to postpone or decline moving their folders, OneDrive periodically reminds them.


* `SilentlyMove`: Silently move Windows known folders to OneDrive. When this policy applies to the device, the OneDrive client automatically redirects the known folders to OneDrive for Business.



Valid Values:

* PromptToMove
* SilentlyMove






|Type                         |Required|Position|PipelineInput|Aliases                      |
|-----------------------------|--------|--------|-------------|-----------------------------|
|`[MoveKnownFolderOptionType]`|false   |named   |False        |OneDriveKnownFolderMoveOption|



#### **Name**

Specify a name for this OneDrive for Business policy.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **O365TenantId**

Specify your Microsoft 365 tenant ID. Find your Microsoft 365 tenant ID (/onedrive/find-your-office-365-tenant-id).






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |AADTenantId|



#### **PreventRedirectKnownFolders**

Set this parameter to `$true` to prevent users from redirecting their Windows known folders back to their PC. It disables the option in OneDrive for Business on the client for users to move these folders back to the device.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ShowNotification**

When you use `SilentlyMove` for the KnownFolderMoveOption parameter, if you set this parameter to `$true`, the OneDrive client notifies the user after it moves their folders.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SupportedPlatform**

Specify a supported platform object to which this policy is applicable. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|true    |named   |False        |SupportedPlatforms|



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
* IResultObject#SMS_ConfigurationPolicy






---


### Notes




---


### Syntax
```PowerShell
New-CMOneDriveBusinessProfile [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-KnownFolderMoveOption {PromptToMove | SilentlyMove}] -Name <String> -O365TenantId <String> [-PreventRedirectKnownFolders <Boolean>] [-ShowNotification <Boolean>] -SupportedPlatform <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
