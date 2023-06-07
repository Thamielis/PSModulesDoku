New-CMMicrosoftEdgeBrowserProfiles
----------------------------------




### Synopsis
Create a policy to manage Microsoft Edge Legacy browser settings.



---


### Description

Create a policy to manage Microsoft Edge Legacy browser settings. This policy only applies to clients on Windows 10, version 1703 or later, and Microsoft Edge Legacy version 45 and earlier. For more information, see Configure Microsoft Edge Legacy settings in Configuration Manager (/mem/configmgr/compliance/deploy-use/browser-profiles). This article also includes more details on the specific policy settings.



For more information on managing Microsoft Edge version 77 or later with Configuration Manager, see Deploy Microsoft Edge, version 77 and later (/mem/configmgr/apps/deploy-use/deploy-edge). For more information on configuring policies for Microsoft Edge version 77 or later, see [Microsoft Edge - Policies](/DeployEdge/microsoft-edge-policies).



---


### Related Links
* [Get-CMMicrosoftEdgeBrowserProfiles](Get-CMMicrosoftEdgeBrowserProfiles)



* [Set-CMMicrosoftEdgeBrowserProfiles](Set-CMMicrosoftEdgeBrowserProfiles)



* [Configure Microsoft Edge Legacy settings in Configuration Manager](Configure Microsoft Edge Legacy settings in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
$os1 = Get-CMSupportedPlatform -Name "*Windows*10*" -Fast

New-CMMicrosoftEdgeBrowserProfiles -Name "Edge1" -SupportedPlatform $os1 -AllowAddressBarDropDown Allow -AllowAutoFill Allow -AllowCookies Allow -AllowDeveloperTools Allow -AllowDoNotTrack Allow -AllowExtensions Allow -AllowPasswordManager Allow -AllowPopups Allow -AllowSearchSuggestions Allow -AllowSmartScreen Allow -ClearBrowsingDataOnExit Allow -Description "Edge1" -PreventOverrideFiles Allow -PreventPromptOverride Allow -SendIntranetTrafficToIE Allow -SetEdgeBrowserAsDefault Configured -SyncFavoritesIEAndEdge Allow
```



---


### Parameters
#### **AllowAddressBarDropDown**

Configure the setting to Allow address bar drop-down .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |



#### **AllowAutoFill**

Configure the setting to Allow autofill .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |



#### **AllowCookies**

Configure the setting to Allow cookies .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |



#### **AllowDeveloperTools**

Configure the setting to Allow Developer Tools .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |



#### **AllowDoNotTrack**

Configure the setting to Allow Do Not Track headers .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |



#### **AllowExtensions**

Configure the setting to Allow extensions .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |



#### **AllowPasswordManager**

Configure the setting to Allow password manager .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |



#### **AllowPopups**

Configure the setting to Allow pop-up blocker .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |



#### **AllowSearchSuggestions**

Configure the setting to Allow search suggestions in address bar .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|Aliases                           |
|--------------------------|--------|--------|-------------|----------------------------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |AllowSearchSuggestionsinAddressBar|



#### **AllowSmartScreen**

Configure the Microsoft Defender SmartScreen setting to Allow SmartScreen .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |



#### **ClearBrowsingDataOnExit**

Configure the setting to Allow clear browsing data on exit .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |



#### **Description**

Specify an optional description for the browser profile policy.






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



#### **Name**

Specify a name for the browser profile policy.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **PreventOverrideFiles**

Configure the Microsoft Defender SmartScreen setting: Users can override SmartScreen prompt for files .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|Aliases                                 |
|--------------------------|--------|--------|-------------|----------------------------------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |PreventSmartScreenPromptOverrideForFiles|



#### **PreventPromptOverride**

Configure the Microsoft Defender SmartScreen setting: Users can override SmartScreen prompt for sites .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|Aliases                         |
|--------------------------|--------|--------|-------------|--------------------------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |PreventSmartScreenPromptOverride|



#### **SendIntranetTrafficToIE**

Configure the setting to Allow send intranet traffic to Internet Explorer .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|Aliases                              |
|--------------------------|--------|--------|-------------|-------------------------------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |SendIntranetTrafficToInternetExplorer|



#### **SetEdgeBrowserAsDefault**

Configure the setting to Set Microsoft Edge browser as default . If you configure this setting, Configuration Manager configures the Windows 10 default app setting for web browser to Microsoft Edge Legacy.



Valid Values:

* Configured
* NotConfigured






|Type                               |Required|Position|PipelineInput|
|-----------------------------------|--------|--------|-------------|
|`[EdgeBrowserAsDefaultSettingType]`|false   |named   |False        |



#### **SupportedPlatform**

Specify a supported platform object to which this policy is applicable. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|true    |named   |False        |SupportedPlatforms|



#### **SyncFavoritesIEAndEdge**

Configure the setting to Allow sync favorites between Microsoft browsers .



Valid Values:

* Allow
* NotAllow
* NotConfigured






|Type                      |Required|Position|PipelineInput|Aliases                               |
|--------------------------|--------|--------|-------------|--------------------------------------|
|`[EdgeBrowserSettingType]`|false   |named   |False        |SyncFavoritesBetweenIEAndMicrosoftEdge|



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
New-CMMicrosoftEdgeBrowserProfiles [-AllowAddressBarDropDown {Allow | NotAllow | NotConfigured}] [-AllowAutoFill {Allow | NotAllow | NotConfigured}] [-AllowCookies {Allow | NotAllow | NotConfigured}] [-AllowDeveloperTools {Allow | NotAllow | NotConfigured}] [-AllowDoNotTrack {Allow | NotAllow | NotConfigured}] [-AllowExtensions {Allow | NotAllow | NotConfigured}] [-AllowPasswordManager {Allow | NotAllow | NotConfigured}] [-AllowPopups {Allow | NotAllow | NotConfigured}] [-AllowSearchSuggestions {Allow | NotAllow | NotConfigured}] [-AllowSmartScreen {Allow | NotAllow | NotConfigured}] [-ClearBrowsingDataOnExit {Allow | NotAllow | NotConfigured}] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PreventOverrideFiles {Allow | NotAllow | NotConfigured}] [-PreventPromptOverride {Allow | NotAllow | NotConfigured}] [-SendIntranetTrafficToIE {Allow | NotAllow | NotConfigured}] [-SetEdgeBrowserAsDefault {Configured | NotConfigured}] -SupportedPlatform <IResultObject[]> [-SyncFavoritesIEAndEdge {Allow | NotAllow | NotConfigured}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
