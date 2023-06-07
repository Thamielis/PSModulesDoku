Set-CMUserDataAndProfileConfigurationItem
-----------------------------------------




### Synopsis
Modifies a user data and profile configuration item.



---


### Description

The Set-CMUserDataAndProfileConfigurationItem cmdlet modifies a user data and profile configuration item that can apply to Windows 8 computers. A configuration item can manage folder redirection, offline folders, and roaming user profiles. You can create a configuration item by using the New-CMUserDataAndProfileConfigurationItem (New-CMUserDataAndProfileConfigurationItem.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMUserDataAndProfileConfigurationItem](New-CMUserDataAndProfileConfigurationItem)





---


### Examples
#### Example 1: Modify a configuration item
```PowerShell
PS XYZ:\> Set-CMUserDataAndProfileConfigurationItem -Name "CMUDaPCI001" -NewName "CMUDaPCI0073" -ConfigureFolderRedirection $False -ConfigureOffineFile $False -ConfigureRoamingUserProfile $False -Description "User data and profile configuration information"
```
This command modifies the configuration item named CMUDaPCI001, changing its name to CMUDaPCI0073. The command also sets values for whether the configuration item specifies folder redirection, offline folders, and roaming profiles, and it provides a description for the configuration item.


---


### Parameters
#### **AccessPolicy**

Indicates whether this configuration item manages profile access settings for roaming profiles.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AddAdminGroupToRupEnabled**

Indicates whether to grant the Administrators group access to roaming profile folders.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowAllDevice**

Indicates whether to allow roaming profiles on all devices. If this value is $False, roaming profiles apply only to the primary device for a user.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowCrossForestUserPolicy**

Indicates whether to permit user policies to roam across Active Directory forests that have a trust relationship with the current forest.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AppDataRoaming**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                                                                                     |
|-------------------------|--------|--------|-------------|------------------------------------------------------------------------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForApplicationData<br/>FolderRedirectionUserConfigurationForAppDataRoaming|



#### **BackgroundSynchronization**

Specifies a background synchronization type for file in offline mode.


The acceptable values for this parameter are:


* Disabled


* Enabled


* NotConfigured



Valid Values:

* Enabled
* Disabled
* NotConfigured






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[SynchronizationType]`|false   |named   |False        |



#### **BackgroundUploadHour**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ConfigureFolderRedirection**

Indicates whether the configuration item includes settings for folder redirection.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ConfigureOfflineFile**








|Type       |Required|Position|PipelineInput|Aliases            |
|-----------|--------|--------|-------------|-------------------|
|`[Boolean]`|false   |named   |False        |ConfigureOffineFile|



#### **ConfigureRoamingUserProfile**

Indicates whether the configuration item includes settings for roaming user profiles.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ConnectionTransferRate**

Specifies a connection transfer rate.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Contact**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                                   |
|-------------------------|--------|--------|-------------|----------------------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForContacts<br/>Contacts|



#### **DeleteProfileOlderDays**

Specifies the number of days to keep a user profile since the last time someone used it. A computer deletes an older profile when it restarts.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DeleteRoamingCacheEnabled**

Indicates whether to delete cached copies of roaming user profiles. The default for this parameter is $False.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Description**

Specifies a description for the configuration item.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



#### **Desktop**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                     |
|-------------------------|--------|--------|-------------|--------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForDesktop|



#### **DetectSlowLink**

Indicates whether to detect slow links.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DeviceType**

Specifies the applicability of folder redirection for user devices. The acceptable values for this parameter are:


* FolderRedirectionOnAnyDeviceCachingOnPrimaryDevicesOnly. Folder redirection for any user device, but caching only on the primary device for a user. - OnAnyDevice. Folder redirection and caching on any device. - OnlyOnPrimaryDevices. Folder redirection and caching on the primary device for a user.



Valid Values:

* OnAnyDevice
* OnlyOnPrimaryDevices
* FolderRedirectionOnAnyDeviceCachingOnPrimaryDevicesOnly






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[DeviceType]`|false   |named   |False        |



#### **Digest**








|Type                 |Required|Position|PipelineInput |
|---------------------|--------|--------|--------------|
|`[ConfigurationItem]`|false   |named   |True (ByValue)|



#### **DigestPath**








|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|false   |named   |False        |DesiredConfigurationDigestPath|



#### **DigestXml**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableMakeOffline**

Indicates whether users can disable the Make Available Offline command.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisableWorkOffline**

Indicates whether users can disable the Work Offline command.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Document**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                                     |
|-------------------------|--------|--------|-------------|------------------------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForDocuments<br/>Documents|



#### **Download**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                                     |
|-------------------------|--------|--------|-------------|------------------------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForDownloads<br/>Downloads|



#### **EnableOfflineFile**

Indicates whether this configuration item enables use of offline files.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSlowLink**

Indicates whether the configuration enables work with offline files over a slow link.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ErrorDays**

Specifies the number of days to wait before the profile creates an error.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ExcludeList**

Specifies an array of folders. The configuration item excludes these folders from roaming profiles.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **Favorite**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                                     |
|-------------------------|--------|--------|-------------|------------------------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForFavorites<br/>Favorites|



#### **FileSynchronization**

Specifies a file synchronization type for metered networks for work in offline mode. The acceptable values for this parameter are:


* Disabled


* Enabled


* NotConfigured



Valid Values:

* Enabled
* Disabled
* NotConfigured






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[SynchronizationType]`|false   |named   |False        |



#### **ForceUnloadDisabled**

Indicates whether to disable forced unload of a user profile at logoff. The default value for this parameter is $False.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GrantExclusiveRight**

Indicates whether to grant the user exclusive permissions to a redirected folder.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Id**

Specifies an array of IDs for user data and profile configuration items.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a user data and profile configuration item object. To obtain a configuration item object, use the Get-CMUserDataAndProfileConfigurationItem (Get-CMUserDataAndProfileConfigurationItem.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **LeaveFolderNewLocation**

Indicates whether to leave the folder in the redirected location in the event that you remove this configuration item.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **LimitDisk**

Specifies a limit, in megabytes, for the disk space used for offline files.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Link**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                             |
|-------------------------|--------|--------|-------------|----------------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForLinks<br/>Links|



#### **ManageAdvancedSetting**

Indicates whether this configuration item manages advanced settings for folder redirection. Specify values for any of the following parameters:


* GrantExclusiveRight - MoveContent - LeaveFolderNewLocation - MoveCachedFolder






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ManageSlowLink**

Indicates whether this profile item manages slow links.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MoveCachedFolder**

Indicates whether to move the cached folder when the path updates on the server.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MoveContent**

Indicates whether to move the contents of redirected folders to the new location.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Music**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                   |
|-------------------------|--------|--------|-------------|------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForMusic|



#### **Name**

Specifies an array of names of user data and profile configuration items.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **NewName**

Specifies a new name for the configuration item.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OfflineFile**

Specifies an array of Administrative user assigned offline folders, as UNC paths as follows: \\server\share\%UserName%.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **OnlyAllowLocalProfile**








|Type       |Required|Position|PipelineInput|Aliases               |
|-----------|--------|--------|-------------|----------------------|
|`[Boolean]`|false   |named   |False        |OnlyAllowLocalProfiles|



#### **OwnerCheckDisabled**

Indicates whether the configuration item does not check for ownership of roaming profile folders.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Picture**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                                   |
|-------------------------|--------|--------|-------------|----------------------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForPictures<br/>Pictures|



#### **ProfileUploadDisabled**

Indicates whether to disable uploading of profiles.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SavedGame**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                                       |
|-------------------------|--------|--------|-------------|--------------------------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForSavedGames<br/>SavedGames|



#### **Search**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                                   |
|-------------------------|--------|--------|-------------|----------------------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForSearches<br/>Searches|



#### **SlowLink**

Specifies a value for a slow link.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SlowLinkUIEnabled**

Indicates whether to enable the user logon prompt to allow profile download when a device detects a slow link.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SpecifiedLocation**

Specifies a specified location.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SpecifyTime**

Specifies a time for background upload of the user hive.



Valid Values:

* 12:00 AM
* 1:00 PM
* 2:00 PM
* 3:00 PM
* 4:00 PM
* 5:00 PM
* 6:00 PM
* 7:00 PM
* 8:00 PM
* 9:00 PM
* 10:00 PM
* 11:00 PM
* 12:00 PM






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SpecifyTimeMin**








|Type     |Required|Position|PipelineInput|Aliases            |
|---------|--------|--------|-------------|-------------------|
|`[Int32]`|false   |named   |False        |SpecifyTimeInterval|



#### **StartMenu**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                       |
|-------------------------|--------|--------|-------------|----------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForStartMenu|



#### **SynchronizationList**

Specifies an array of folders. The configuration item specifies these subfolders of Appdata\Roaming to synchronize only at logon and logoff.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **SynchronizationPolicy**

Indicates whether to use a synchronization policy.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SyncMins**








|Type     |Required|Position|PipelineInput|Aliases                |
|---------|--------|--------|-------------|-----------------------|
|`[Int32]`|false   |named   |False        |SynchronizationInterval|



#### **TempProfileLogonBlocked**

Indicates whether to block users from logging on by using a temporary profile.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **TimeOut**

Specifies a timeout value.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UseCommonAlert**

Indicates whether to use common alerts.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseSpecifiedLocation**

Indicates whether to use the specified location referred to by the SpecifiedLocation parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Video**





Valid Values:

* RedirectToRemote
* RedirectToLocal
* DoNotManage






|Type                     |Required|Position|PipelineInput|Aliases                                               |
|-------------------------|--------|--------|-------------|------------------------------------------------------|
|`[FolderRedirectionType]`|false   |named   |False        |FolderRedirectionUserConfigurationForVideos<br/>Videos|



#### **WaitForNetworkSec**








|Type     |Required|Position|PipelineInput|Aliases                |
|---------|--------|--------|-------------|-----------------------|
|`[Int32]`|false   |named   |False        |WaitForNetworkInSeconds|



#### **WarningDays**

Specifies the number of days to wait before the profile creates a warning.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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



Microsoft.ConfigurationManagement.DesiredConfigurationManagement.ConfigurationItem





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMUserDataAndProfileConfigurationItem [-Id] <Int32> [-AccessPolicy <Boolean>] [-AddAdminGroupToRupEnabled <Boolean>] [-AllowAllDevice <Boolean>] [-AllowCrossForestUserPolicy <Boolean>] [-AppDataRoaming {RedirectToRemote | RedirectToLocal | DoNotManage}] [-BackgroundSynchronization {Enabled | Disabled | NotConfigured}] [-BackgroundUploadHour <Int32>] [-ConfigureFolderRedirection <Boolean>] [-ConfigureOfflineFile <Boolean>] [-ConfigureRoamingUserProfile <Boolean>] [-ConnectionTransferRate <Int32>] [-Contact {RedirectToRemote | RedirectToLocal | DoNotManage}] [-DeleteProfileOlderDays <Int32>] [-DeleteRoamingCacheEnabled <Boolean>] [-Description <String>] [-Desktop {RedirectToRemote | RedirectToLocal | DoNotManage}] [-DetectSlowLink <Boolean>] [-DeviceType {OnAnyDevice | OnlyOnPrimaryDevices | FolderRedirectionOnAnyDeviceCachingOnPrimaryDevicesOnly}] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableMakeOffline <Boolean>] [-DisableWildcardHandling] [-DisableWorkOffline <Boolean>] [-Document {RedirectToRemote | RedirectToLocal | DoNotManage}] [-Download {RedirectToRemote | RedirectToLocal | DoNotManage}] [-EnableOfflineFile <Boolean>] [-EnableSlowLink <Boolean>] [-ErrorDays <Int32>] [-ExcludeList <String[]>] [-Favorite {RedirectToRemote | RedirectToLocal | DoNotManage}] [-FileSynchronization {Enabled | Disabled | NotConfigured}] [-ForceUnloadDisabled <Boolean>] [-ForceWildcardHandling] [-GrantExclusiveRight <Boolean>] [-LeaveFolderNewLocation <Boolean>] [-LimitDisk <Int32>] [-Link {RedirectToRemote | RedirectToLocal | DoNotManage}] [-ManageAdvancedSetting <Boolean>] [-ManageSlowLink <Boolean>] [-MoveCachedFolder <Boolean>] [-MoveContent <Boolean>] [-Music {RedirectToRemote | RedirectToLocal | DoNotManage}] [-NewName <String>] [-OfflineFile <String[]>] [-OnlyAllowLocalProfile <Boolean>] [-OwnerCheckDisabled <Boolean>] [-PassThru] [-Picture {RedirectToRemote | RedirectToLocal | DoNotManage}] [-ProfileUploadDisabled <Boolean>] [-SavedGame {RedirectToRemote | RedirectToLocal | DoNotManage}] [-Search {RedirectToRemote | RedirectToLocal | DoNotManage}] [-SlowLink <Int32>] [-SlowLinkUIEnabled <Boolean>] [-SpecifiedLocation <String>] [-SpecifyTime {12:00 AM | 1:00 PM | 2:00 PM | 3:00 PM | 4:00 PM | 5:00 PM | 6:00 PM | 7:00 PM | 8:00 PM | 9:00 PM | 10:00 PM | 11:00 PM | 12:00 PM}] [-SpecifyTimeMin <Int32>] [-StartMenu {RedirectToRemote | RedirectToLocal | DoNotManage}] [-SynchronizationList <String[]>] [-SynchronizationPolicy <Boolean>] [-SyncMins <Int32>] [-TempProfileLogonBlocked <Boolean>] [-TimeOut <Int32>] [-UseCommonAlert <Boolean>] [-UseSpecifiedLocation <Boolean>] [-Video {RedirectToRemote | RedirectToLocal | DoNotManage}] [-WaitForNetworkSec <Int32>] [-WarningDays <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMUserDataAndProfileConfigurationItem [-InputObject] <IResultObject> [-AccessPolicy <Boolean>] [-AddAdminGroupToRupEnabled <Boolean>] [-AllowAllDevice <Boolean>] [-AllowCrossForestUserPolicy <Boolean>] [-AppDataRoaming {RedirectToRemote | RedirectToLocal | DoNotManage}] [-BackgroundSynchronization {Enabled | Disabled | NotConfigured}] [-BackgroundUploadHour <Int32>] [-ConfigureFolderRedirection <Boolean>] [-ConfigureOfflineFile <Boolean>] [-ConfigureRoamingUserProfile <Boolean>] [-ConnectionTransferRate <Int32>] [-Contact {RedirectToRemote | RedirectToLocal | DoNotManage}] [-DeleteProfileOlderDays <Int32>] [-DeleteRoamingCacheEnabled <Boolean>] [-Description <String>] [-Desktop {RedirectToRemote | RedirectToLocal | DoNotManage}] [-DetectSlowLink <Boolean>] [-DeviceType {OnAnyDevice | OnlyOnPrimaryDevices | FolderRedirectionOnAnyDeviceCachingOnPrimaryDevicesOnly}] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableMakeOffline <Boolean>] [-DisableWildcardHandling] [-DisableWorkOffline <Boolean>] [-Document {RedirectToRemote | RedirectToLocal | DoNotManage}] [-Download {RedirectToRemote | RedirectToLocal | DoNotManage}] [-EnableOfflineFile <Boolean>] [-EnableSlowLink <Boolean>] [-ErrorDays <Int32>] [-ExcludeList <String[]>] [-Favorite {RedirectToRemote | RedirectToLocal | DoNotManage}] [-FileSynchronization {Enabled | Disabled | NotConfigured}] [-ForceUnloadDisabled <Boolean>] [-ForceWildcardHandling] [-GrantExclusiveRight <Boolean>] [-LeaveFolderNewLocation <Boolean>] [-LimitDisk <Int32>] [-Link {RedirectToRemote | RedirectToLocal | DoNotManage}] [-ManageAdvancedSetting <Boolean>] [-ManageSlowLink <Boolean>] [-MoveCachedFolder <Boolean>] [-MoveContent <Boolean>] [-Music {RedirectToRemote | RedirectToLocal | DoNotManage}] [-NewName <String>] [-OfflineFile <String[]>] [-OnlyAllowLocalProfile <Boolean>] [-OwnerCheckDisabled <Boolean>] [-PassThru] [-Picture {RedirectToRemote | RedirectToLocal | DoNotManage}] [-ProfileUploadDisabled <Boolean>] [-SavedGame {RedirectToRemote | RedirectToLocal | DoNotManage}] [-Search {RedirectToRemote | RedirectToLocal | DoNotManage}] [-SlowLink <Int32>] [-SlowLinkUIEnabled <Boolean>] [-SpecifiedLocation <String>] [-SpecifyTime {12:00 AM | 1:00 PM | 2:00 PM | 3:00 PM | 4:00 PM | 5:00 PM | 6:00 PM | 7:00 PM | 8:00 PM | 9:00 PM | 10:00 PM | 11:00 PM | 12:00 PM}] [-SpecifyTimeMin <Int32>] [-StartMenu {RedirectToRemote | RedirectToLocal | DoNotManage}] [-SynchronizationList <String[]>] [-SynchronizationPolicy <Boolean>] [-SyncMins <Int32>] [-TempProfileLogonBlocked <Boolean>] [-TimeOut <Int32>] [-UseCommonAlert <Boolean>] [-UseSpecifiedLocation <Boolean>] [-Video {RedirectToRemote | RedirectToLocal | DoNotManage}] [-WaitForNetworkSec <Int32>] [-WarningDays <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMUserDataAndProfileConfigurationItem [-Name] <String> [-AccessPolicy <Boolean>] [-AddAdminGroupToRupEnabled <Boolean>] [-AllowAllDevice <Boolean>] [-AllowCrossForestUserPolicy <Boolean>] [-AppDataRoaming {RedirectToRemote | RedirectToLocal | DoNotManage}] [-BackgroundSynchronization {Enabled | Disabled | NotConfigured}] [-BackgroundUploadHour <Int32>] [-ConfigureFolderRedirection <Boolean>] [-ConfigureOfflineFile <Boolean>] [-ConfigureRoamingUserProfile <Boolean>] [-ConnectionTransferRate <Int32>] [-Contact {RedirectToRemote | RedirectToLocal | DoNotManage}] [-DeleteProfileOlderDays <Int32>] [-DeleteRoamingCacheEnabled <Boolean>] [-Description <String>] [-Desktop {RedirectToRemote | RedirectToLocal | DoNotManage}] [-DetectSlowLink <Boolean>] [-DeviceType {OnAnyDevice | OnlyOnPrimaryDevices | FolderRedirectionOnAnyDeviceCachingOnPrimaryDevicesOnly}] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableMakeOffline <Boolean>] [-DisableWildcardHandling] [-DisableWorkOffline <Boolean>] [-Document {RedirectToRemote | RedirectToLocal | DoNotManage}] [-Download {RedirectToRemote | RedirectToLocal | DoNotManage}] [-EnableOfflineFile <Boolean>] [-EnableSlowLink <Boolean>] [-ErrorDays <Int32>] [-ExcludeList <String[]>] [-Favorite {RedirectToRemote | RedirectToLocal | DoNotManage}] [-FileSynchronization {Enabled | Disabled | NotConfigured}] [-ForceUnloadDisabled <Boolean>] [-ForceWildcardHandling] [-GrantExclusiveRight <Boolean>] [-LeaveFolderNewLocation <Boolean>] [-LimitDisk <Int32>] [-Link {RedirectToRemote | RedirectToLocal | DoNotManage}] [-ManageAdvancedSetting <Boolean>] [-ManageSlowLink <Boolean>] [-MoveCachedFolder <Boolean>] [-MoveContent <Boolean>] [-Music {RedirectToRemote | RedirectToLocal | DoNotManage}] [-NewName <String>] [-OfflineFile <String[]>] [-OnlyAllowLocalProfile <Boolean>] [-OwnerCheckDisabled <Boolean>] [-PassThru] [-Picture {RedirectToRemote | RedirectToLocal | DoNotManage}] [-ProfileUploadDisabled <Boolean>] [-SavedGame {RedirectToRemote | RedirectToLocal | DoNotManage}] [-Search {RedirectToRemote | RedirectToLocal | DoNotManage}] [-SlowLink <Int32>] [-SlowLinkUIEnabled <Boolean>] [-SpecifiedLocation <String>] [-SpecifyTime {12:00 AM | 1:00 PM | 2:00 PM | 3:00 PM | 4:00 PM | 5:00 PM | 6:00 PM | 7:00 PM | 8:00 PM | 9:00 PM | 10:00 PM | 11:00 PM | 12:00 PM}] [-SpecifyTimeMin <Int32>] [-StartMenu {RedirectToRemote | RedirectToLocal | DoNotManage}] [-SynchronizationList <String[]>] [-SynchronizationPolicy <Boolean>] [-SyncMins <Int32>] [-TempProfileLogonBlocked <Boolean>] [-TimeOut <Int32>] [-UseCommonAlert <Boolean>] [-UseSpecifiedLocation <Boolean>] [-Video {RedirectToRemote | RedirectToLocal | DoNotManage}] [-WaitForNetworkSec <Int32>] [-WarningDays <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
