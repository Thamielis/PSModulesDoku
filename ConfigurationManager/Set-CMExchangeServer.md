Set-CMExchangeServer
--------------------




### Synopsis
Changes settings for an Exchange server.



---


### Description

The Set-CMExchangeServer cmdlet changes settings for a Microsoft Exchange Server.



Configuration Manager works with Exchange Server to manage mobile devices that cannot run Configuration Manager clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMExchangeServer](Get-CMExchangeServer)



* [New-CMExchangeServer](New-CMExchangeServer)



* [New-CMExchangeConnectorApplicationSetting](New-CMExchangeConnectorApplicationSetting)



* [New-CMExchangeConnectorEmailManagementSetting](New-CMExchangeConnectorEmailManagementSetting)



* [New-CMExchangeConnectorSecuritySetting](New-CMExchangeConnectorSecuritySetting)



* [Remove-CMExchangeServer](Remove-CMExchangeServer)



* [Sync-CMExchangeServer](Sync-CMExchangeServer)





---


### Examples
#### Example 1: Change settings for an nextref_exchange
```PowerShell
PS XYZ:\> $Gs= New-CMExchangeConnectorGeneralSetting -AllowInternetShare $True -AllowDesktopSync $True -AllowNonProvision $True -RefreshInterval 4
PS XYZ:\> $Ps= New-CMExchangeConnectorPasswordSetting -PasswordEnabled $True -MinimumPasswordLength 8 -PasswordExpiration 51 -PasswordHistory 21 -WipeAfterFailedAttempt 6 -MaximumIdleTimeMinutes 41 -PasswordComplexity
PS XYZ:\> $Em = New-CMExchangeConnectorEmailManagementSetting -ConsumerEmail $True -MaximumEmailAge OneDay -MaximumCalenderAge ThreeMonths -PushWhenRoaming $True -AllowHtmlEmail $True -EmailAttachmentPolicy $True -MaximumSizeTextEmail 401 -MaximumSizeHtmlEmail 402 -MaximumSizeAttachment 24
PS XYZ:\> $Ss = New-CMExchangeConnectorSecuritySetting -RemoteDesktop $True -StorageCard $True -Camera $True -Bluetooth $False -WiFiConnection HandsfreeOnly -Infra $False -Browser $False -StorageCardEncrypt $False -FileEncrypt $False -TextMessage $False
PS XYZ:\> $As= New-CMExchangeConnectorApplicationSetting -UnsignedInstall $True -UnsignedApplication $False -BlockedApplication "App01","App02"
PS XYZ:\> Set-CMExchangeServer -SiteCode "CM2" -ServerAddress "https://www.contoso.com/powershell" -NewServerAddress "www.fabrikam.com" -UserName "ElisaDaugherty@contoso.com" -DeltaSyncInterval 124 -MaximumInactiveDay 26 -FindAll -AllowExternalDeviceManagement $False -EnableAccessRule $True -AccessLevel Allow -EmailAddress "EvanNarvaez@fabrikam.com","DavidChew@contosco.com" -GeneralSetting $Gs -PasswordSetting $Ps -EmailManagementSetting $Em -SecuritySetting $Ss -ApplicationSetting $As
```
The first command uses the New-CMExchangeConnectorGeneralSetting cmdlet to add new settings to an Exchange Server connector in Configuration Manager, and stores the settings in the $Gs variable.<!--505995-->


The second command uses the New-CMExchangeConnectorPasswordSetting (New-CMExchangeConnectorPasswordSetting.md)cmdlet adds new password settings to an Exchange Server connector in Configuration Manager, and stores the password settings in the $Ps variable.


The third command uses the New-CMExchangeConnectorEmailManagementSetting (New-CMExchangeConnectorEmailManagementSetting.md)cmdlet creates a set of e-mail management settings for a mobile device that uses an Exchange Server connector, and stores the password settings in the $Em variable.


The fourth command uses the New-CMExchangeConnectorSecuritySetting (New-CMExchangeConnectorSecuritySetting.md)cmdlet configures security options for an Exchange Server connector in Configuration Manager, and security settings in the $Ss variable.


The fifth command uses the New-CMExchangeConnectorApplicationSetting (New-CMExchangeConnectorApplicationSetting.md)cmdlet creates application-related settings for a mobile device that uses an Exchange Server connector, and stores the application settings in the $As variable.


The final command changes settings for an Exchange Server for the Configuration Manager site that has the site code CM2. The command specifies the general settings for the Exchange Server connector stored in $Gs. The command specifies password settings for the Exchange Server connector stored in $Ps. The command specifies a set of e-mail management settings for the Exchange Server connector stored in $Em. The command specifies the security options for the Exchange Server connector stored in $Ss. The command specifies application-related settings for a mobile device stored in $As.


---


### Parameters
#### **AccessLevel**

Specifies the type of access for the mobile devices. Access level applies to a mobile device that is not managed by a rule. Valid values are:


* Allow


* Block


* Quarantine



Valid Values:

* Allow
* Block
* Quarantine






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[AccessLevelType]`|false   |named   |False        |



#### **AccessRule**








|Type                             |Required|Position|PipelineInput|Aliases    |
|---------------------------------|--------|--------|-------------|-----------|
|`[ExchangeConnectorAccessRule[]]`|false   |named   |False        |AccessRules|



#### **ActiveDirectoryContainer**

Specifies an array of names of Active Directory containers. When this parameter appears, the Exchange Server connector searches for the device only in the Active Directory containers.






|Type        |Required|Position|PipelineInput|Aliases                  |
|------------|--------|--------|-------------|-------------------------|
|`[String[]]`|false   |named   |False        |ActiveDirectoryContainers|



#### **AllowExternalDeviceManagement**

Indicates whether an external device management program can manage the device.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ApplicationSetting**

Specifies application settings, such as allow or deny the installation of applications. For each dictionary entry in the array, specify the setting name as the key the configuration as the value. Valid values are: AllowUnsignedApplications, AllowUnsignedInstallationPackages, or Block a specific application.






|Type                                   |Required|Position|PipelineInput|
|---------------------------------------|--------|--------|-------------|
|`[ExchangeConnectorApplicationSetting]`|false   |named   |False        |



#### **DeltaSyncMins**








|Type     |Required|Position|PipelineInput|Aliases          |
|---------|--------|--------|-------------|-----------------|
|`[Int32]`|false   |named   |False        |DeltaSyncInterval|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EmailAddress**

Specifies an array of email addresses.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|false   |named   |False        |EmailAddresses|



#### **EmailManagementSetting**

Specifies email management settings, such as synchronization schedule, message format, and size of attachments. For each dictionary entry in the array, specify the setting name as the key and the configuration as the value.






|Type                                       |Required|Position|PipelineInput|
|-------------------------------------------|--------|--------|-------------|
|`[ExchangeConnectorEmailManagementSetting]`|false   |named   |False        |



#### **EnableAccessRule**

Indicates whether to enable an access rule.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ExchangeClientAccessServer**

Specifies Exchange Client Access servers, as key-value pairs.






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[Dictionary`2[]]`|false   |named   |False        |



#### **FindAll**

Indicates that the discovery process find all mobile devices in an Exchange organization.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FullSyncSchedule**

Specifies a result object that schedules the full discovery time for an Exchange Server connector.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **GeneralSetting**

Specifies general settings for mobile devices that use the Exchange Server Connector. Settings you can specify for this parameter include:


* RequireManualSyncWhenRoaming


* RequireStorageCardEncryption


* UnapprovedInROMApplicationList


* DevicePolicyRefreshInterval


* MaxInactivityTimeDeviceLock






|Type                               |Required|Position|PipelineInput|
|-----------------------------------|--------|--------|-------------|
|`[ExchangeConnectorGeneralSetting]`|false   |named   |False        |



#### **IsHosted**

Indicates that the Exchange Server connector configuration is for a hosted or on-premise Exchange Server.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MaximumInactiveDays**








|Type     |Required|Position|PipelineInput|Aliases           |
|---------|--------|--------|-------------|------------------|
|`[Int32]`|false   |named   |False        |MaximumInactiveDay|



#### **NewServerAddress**

Specifies a new server address for an Exchange server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NotificationUserName**

{{ Fill NotificationUserName Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PasswordSetting**

Specifies general password settings. Settings you can specify for this parameter include:


* AlphanumericDevicePasswordRequired


* DevicePasswordEnabled


* DevicePasswordExpiration


* DevicePasswordHistory


* MaxDevicePasswordFailedAttempts


* PasswordRecoveryEnabled


* MinDevicePasswordComplexCharacters


* MinDevicePasswordLength


* AlphanumericDevicePasswordRequired


* AllowSimpleDevicePassword






|Type                                |Required|Position|PipelineInput|
|------------------------------------|--------|--------|-------------|
|`[ExchangeConnectorPasswordSetting]`|false   |named   |False        |



#### **SecuritySetting**

Specifies a dictionary of security settings. Settings you can specify for this parameter include:


* AllowBluetooth


* AllowBrowser


* AllowCamera


* AllowDesktopSync


* AllowInternetSharing


* AllowIrDA


* AllowNonProvisionableDevices


* AllowRemoteDesktop


* AllowStorageCard


* AllowTextMessaging


* AllowWiFi






|Type                                |Required|Position|PipelineInput|
|------------------------------------|--------|--------|-------------|
|`[ExchangeConnectorSecuritySetting]`|false   |named   |False        |



#### **ServerAddress**

Specifies the address of the Exchange Server for which the cmdlet configures the Exchange Server connector.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SiteCode**

Specifies the Exchange Server by using a site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserName**

Specifies the user name that the connector uses to connect to the Exchange Server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMExchangeServer [-AccessLevel {Allow | Block | Quarantine}] [-AccessRule <ExchangeConnectorAccessRule[]>] [-ActiveDirectoryContainer <String[]>] [-AllowExternalDeviceManagement <Boolean>] [-ApplicationSetting <ExchangeConnectorApplicationSetting>] [-DeltaSyncMins <Int32>] [-DisableWildcardHandling] [-EmailAddress <String[]>] [-EmailManagementSetting <ExchangeConnectorEmailManagementSetting>] [-EnableAccessRule <Boolean>] [-ExchangeClientAccessServer <Dictionary`2[]>] [-FindAll] [-ForceWildcardHandling] [-FullSyncSchedule <IResultObject>] [-GeneralSetting <ExchangeConnectorGeneralSetting>] [-IsHosted <Boolean>] [-MaximumInactiveDays <Int32>] [-NewServerAddress <String>] [-NotificationUserName <String>] [-PasswordSetting <ExchangeConnectorPasswordSetting>] [-SecuritySetting <ExchangeConnectorSecuritySetting>] -ServerAddress <String> [-SiteCode <String>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
