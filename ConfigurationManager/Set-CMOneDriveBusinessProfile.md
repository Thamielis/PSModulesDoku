Set-CMOneDriveBusinessProfile
-----------------------------




### Synopsis
Configure a OneDrive for Business profile policy.



---


### Description

Configure a OneDrive for Business profile policy. Use this policy to move Windows known folders to OneDrive for Business. These folders include Desktop, Documents, and Pictures. In each profile, you can specify settings for moving the Windows known folders. For more information on OneDrive for Business, see Redirect and move Windows known folders to OneDrive (/onedrive/redirect-known-folders).



For more information on this Configuration Manager policy, see OneDrive for Business profiles (/mem/configmgr/compliance/deploy-use/onedrive-profile).



---


### Related Links
* [Get-CMOneDriveBusinessProfile](Get-CMOneDriveBusinessProfile)



* [New-CMOneDriveBusinessProfile](New-CMOneDriveBusinessProfile)



* [OneDrive for Business profiles](OneDrive for Business profiles)





---


### Examples
#### Example 1
```PowerShell
$Plats2 = Get-CMSupportedPlatform -Name "All Windows 10 *" -Fast -Platform "X64"

Set-CMOneDriveBusinessProfile -Name "ODfB policy" -ClearSupportedPlatform -AddSupportedPlatform $Plats2 -O365TenantId "05d683b9-caed-4eea-b229-45f72b89ca05" -KnownFolderMoveOption SilentlyMove -ShowNotification $true -PreventRedirectKnownFolders $true
```



---


### Parameters
#### **AddSupportedPlatform**

Specify a supported platform object to which this policy is applicable. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases              |
|-------------------|--------|--------|-------------|---------------------|
|`[IResultObject[]]`|false   |named   |False        |AddSupportedPlatforms|



#### **ClearSupportedPlatform**

Add this parameter to clear the current list of supported platforms.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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



#### **Id**

Specify the CI ID of the OneDrive for Business policy to configure. The format is a five- to seven-digit number, for example `403823`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CI_ID<br/>CIId|



#### **InputObject**

Specify a OneDrive for Business policy object to configure. To get this object, use the Get-CMOneDriveBusinessProfile (Get-CMOneDriveBusinessProfile.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases               |
|-----------------|--------|--------|--------------|----------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|OneDriveBusinessPolicy|



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

Specify the name of the OneDrive for Business policy to configure.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **NewName**

To rename this OneDrive for Business policy, specify a new name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **O365TenantId**

Specify your Microsoft 365 tenant ID. Find your Microsoft 365 tenant ID (/onedrive/find-your-office-365-tenant-id).






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |AADTenantId|



#### **PreventRedirectKnownFolders**

Set this parameter to `$true` to prevent users from redirecting their Windows known folders back to their PC. It disables the option in OneDrive for Business on the client for users to move these folders back to the device.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RemoveSupportedPlatform**

Specify a supported platform object to remove from this policy. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                 |
|-------------------|--------|--------|-------------|------------------------|
|`[IResultObject[]]`|false   |named   |False        |RemoveSupportedPlatforms|



#### **ShowNotification**

When you use `SilentlyMove` for the KnownFolderMoveOption parameter, if you set this parameter to `$true`, the OneDrive client notifies the user after it moves their folders.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* IResultObject#SMS_ConfigurationPolicy






---


### Notes




---


### Syntax
```PowerShell
Set-CMOneDriveBusinessProfile [-AddSupportedPlatform <IResultObject[]>] [-ClearSupportedPlatform] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-KnownFolderMoveOption {PromptToMove | SilentlyMove}] [-NewName <String>] [-O365TenantId <String>] [-PreventRedirectKnownFolders <Boolean>] [-RemoveSupportedPlatform <IResultObject[]>] [-ShowNotification <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMOneDriveBusinessProfile [-AddSupportedPlatform <IResultObject[]>] [-ClearSupportedPlatform] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-KnownFolderMoveOption {PromptToMove | SilentlyMove}] [-NewName <String>] [-O365TenantId <String>] [-PreventRedirectKnownFolders <Boolean>] [-RemoveSupportedPlatform <IResultObject[]>] [-ShowNotification <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMOneDriveBusinessProfile [-AddSupportedPlatform <IResultObject[]>] [-ClearSupportedPlatform] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-KnownFolderMoveOption {PromptToMove | SilentlyMove}] -Name <String> [-NewName <String>] [-O365TenantId <String>] [-PreventRedirectKnownFolders <Boolean>] [-RemoveSupportedPlatform <IResultObject[]>] [-ShowNotification <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
