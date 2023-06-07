New-CMExchangeServer
--------------------




### Synopsis
Configures a new Exchange Server connector.



---


### Description

The New-CMExchangeServer cmdlet configures a new Microsoft Exchange Server connector in Configuration Manager. An Exchange Server connector synchronizes and manages the device enrolled by the Exchange Server.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMExchangeServer](Get-CMExchangeServer)



* [Remove-CMExchangeServer](Remove-CMExchangeServer)



* [Set-CMExchangeServer](Set-CMExchangeServer)



* [Sync-CMExchangeServer](Sync-CMExchangeServer)





---


### Examples
#### Example 1: Create an Exchange Server
```PowerShell
PS XYZ:\> $schedule = New-CMSchedule -Start "03/01/2016 11:59 PM" -RecurInterval Days -RecurCount 1
PS XYZ:\> New-CMExchangeServer -ServerAddress "https://exchange.contoso.com" -DeltaSyncInterval 120 -FullSyncSchedule $schedule -IsHosted -SiteCode "ContosoSite"
```
These commands create an Exchange Server with the server address `https://exchange.contoso.com`. To do this, the first command in the example uses the New-CMSchedule cmdlet to create a schedule for doing Exchange synchronizations. This schedule object is stored in a variable $schedule.


The second command then uses New-CMExchangeServer to create the new server as part of the site ContosoSite.


---


### Parameters
#### **AccessLevel**

{{ Fill AccessLevel Description }}



Valid Values:

* Allow
* Block
* Quarantine






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[AccessLevelType]`|false   |named   |False        |



#### **ActiveDirectoryContainer**

Specifies an array of names of Active Directory containers. When this parameter is specified, the Exchange Server connector searches the Active Directory containers for the device.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **AllowExternalDeviceManagement**

Indicates whether an external device management program can manage the device.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ApplicationSetting**

Specifies application settings. For each dictionary entry in the array, specify the setting name as the key and the configuration as the value. Valid values are: AllowUnsignedApplications, AllowUnsignedInstallationPackages, or Block a specific application.






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

{{ Fill EmailAddress Description }}






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|false   |named   |False        |EmailAddresses|



#### **EmailManagementSetting**

Specifies email management settings. For each dictionary entry in the array, specify the setting name as the key and the configuration as the value.






|Type                                       |Required|Position|PipelineInput|
|-------------------------------------------|--------|--------|-------------|
|`[ExchangeConnectorEmailManagementSetting]`|false   |named   |False        |



#### **EnableAccessRule**

{{ Fill EnableAccessRule Description }}






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ExchangeClientAccessServer**

Specifies an array of Exchange Client Access servers, as key-value pairs.






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[Dictionary`2[]]`|false   |named   |False        |



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

Specifies general settings. Valid values are:


* RequireManualSyncWhenRoaming


* RequireStorageCardEncryption


* UnapprovedInROMApplicationList


* DevicePolicyRefreshInterval


* MaxInactivityTimeDeviceLock






|Type                               |Required|Position|PipelineInput|
|-----------------------------------|--------|--------|-------------|
|`[ExchangeConnectorGeneralSetting]`|false   |named   |False        |



#### **Hosted**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IsHosted**

Indicates that the Exchange Server connector configuration is for a hosted or on-premise Exchange Server.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MaximumInactiveDay**

Specifies the interval between times that the Exchange Server connector runs device discovery. The cmdlet checks the last sync time of the devices that Exchange Server manages. If the most recent sync time is older than the current time - MinimumInactiveDay, then the exchange connector does not discover the devices.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **NotificationUserName**

{{ Fill NotificationUserName Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OnPrem**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PasswordSetting**

Specifies password settings. Valid values are:


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

Specifies a dictionary of security settings. Valid values are:


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

Specifies the site code of the Configuration Manager site where a Exchange Server connector runs.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserName**

Specifies the username that the connector uses to connect to the Exchange Server.






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
* IResultObject#SMS_SCI_SCPropertyList






---


### Notes




---


### Syntax
```PowerShell
New-CMExchangeServer [-AccessLevel {Allow | Block | Quarantine}] [-ActiveDirectoryContainer <String[]>] [-AllowExternalDeviceManagement <Boolean>] [-ApplicationSetting <ExchangeConnectorApplicationSetting>] [-DeltaSyncMins <Int32>] [-DisableWildcardHandling] [-EmailAddress <String[]>] [-EmailManagementSetting <ExchangeConnectorEmailManagementSetting>] [-EnableAccessRule <Boolean>] [-ExchangeClientAccessServer <Dictionary`2[]>] [-ForceWildcardHandling] [-FullSyncSchedule <IResultObject>] [-GeneralSetting <ExchangeConnectorGeneralSetting>] [-IsHosted <Boolean>] [-MaximumInactiveDay <Int32>] [-NotificationUserName <String>] [-OnPrem] [-PasswordSetting <ExchangeConnectorPasswordSetting>] [-SecuritySetting <ExchangeConnectorSecuritySetting>] -ServerAddress <String> [-SiteCode <String>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMExchangeServer [-AccessLevel {Allow | Block | Quarantine}] [-ActiveDirectoryContainer <String[]>] [-AllowExternalDeviceManagement <Boolean>] [-ApplicationSetting <ExchangeConnectorApplicationSetting>] [-DeltaSyncMins <Int32>] [-DisableWildcardHandling] [-EmailAddress <String[]>] [-EmailManagementSetting <ExchangeConnectorEmailManagementSetting>] [-EnableAccessRule <Boolean>] [-ForceWildcardHandling] [-FullSyncSchedule <IResultObject>] [-GeneralSetting <ExchangeConnectorGeneralSetting>] [-Hosted] [-IsHosted <Boolean>] [-MaximumInactiveDay <Int32>] [-NotificationUserName <String>] [-PasswordSetting <ExchangeConnectorPasswordSetting>] [-SecuritySetting <ExchangeConnectorSecuritySetting>] -ServerAddress <String> [-SiteCode <String>] -UserName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
