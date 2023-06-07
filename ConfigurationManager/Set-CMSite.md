Set-CMSite
----------




### Synopsis
Configure a Configuration Manager site.



---


### Description

Use the Set-CMSite cmdlet to configure one or more Configuration Manager sites. You can specify a site to configure by using a site name or a site code, or you can use the Get-CMSite (Get-CMSite.md)cmdlet to specify a site.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSite](Get-CMSite)





---


### Examples
#### Example 1: Add a new Active Directory forest
```PowerShell
$newForest = New-CMActiveDirectoryForest -ForestFqdn "tsqa.contoso.com"

Set-CMSite -SiteCode "XYZ" -AddActiveDirectoryForest $newForest
```

#### Example 2: Change the warning alert threshold for free disk space
```PowerShell
Set-CMSite -SiteCode "XYZ" -FreeSpaceThresholdWarningGB 15
```

#### Example 3: Promote a site server to active mode
```PowerShell
Get-CMSite -SiteCode "ADC" | Set-CMSite -PromotePassiveSiteToActive
```

#### Example 4: Add trusted root certification authorities (CA)
```PowerShell
Set-CMSite -SiteCode "XYZ" -AddCertificateByPath "D:\Secure\Certs\cc.cer"
```



---


### Parameters
#### **AddActiveDirectoryForest**

Specifies an array of Active Directory forest objects to which the site is published. To get an Active Directory forest object, use the Get-CMActiveDirectoryForest (Get-CMActiveDirectoryForest.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **AddCertificateByPath**

Specifies an array of paths to trusted root certification authorities.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **AddClientRequestServiceType**

Specifies a service type to add for a port that Configuration Manager uses to communicate with clients in this site.



Valid Values:

* WakeOnLanUdp
* ClientNotificationTcp
* ClientRequestHttpTcp
* ClientRequestsHttpsTcp
* ClientRequestHttpTcpDefault
* ClientRequestsHttpsTcpDefault






|Type                        |Required|Position|PipelineInput|
|----------------------------|--------|--------|-------------|
|`[ClientRequestServiceType]`|false   |named   |False        |



#### **ClientCertificateCustomStoreName**

Specify the store name where the client certificate is located in the Computer store when you don't use the default store of Personal.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ClientCertificateSelectionCriteriaType**

Specifies the criteria type to match in a client certificate when more than one certificate is available. Use the -ClientCertificateSelectionCriteriaValue parameter to specify the value.



Valid Values:

* ClientAuthentication
* CertificateSubjectContainsString
* CertificateSubjectOrSanIncludesAttributes
* CertificateSubjectOrSanIncludesAttributes






|Type                                      |Required|Position|PipelineInput|
|------------------------------------------|--------|--------|-------------|
|`[ClientCertificateSelectionCriteriaType]`|false   |named   |False        |



#### **ClientCertificateSelectionCriteriaValue**

Specifies a value for the -ClientCertificateSelectionCriteriaType parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ClientCheckCertificateRevocationListForSiteSystem**

Indicates whether clients check the Certificate Revocation List (CRL) for site systems.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClientComputerCommunicationType**

Specifies the communication method for the site systems that use IIS. To use HTTPS, the servers need a valid PKI web server certificate for server authentication.



Valid Values:

* HttpsOnly
* HttpsOrHttp






|Type                               |Required|Position|PipelineInput|
|-----------------------------------|--------|--------|-------------|
|`[ClientComputerCommunicationType]`|false   |named   |False        |



#### **Comment**

Specifies a comment for a Configuration Manager site to help identify it.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ConcurrentSendingDelayBeforeRetryingMins**

A site can send data concurrently to multiple sites. If it needs to retry, this integer value specifies the number of minutes to delay before it retries. By default, the value is `1`. Use the -RetryNumberForConcurrentSending parameter to specify the number of retries.






|Type     |Required|Position|PipelineInput|Aliases                                    |
|---------|--------|--------|-------------|-------------------------------------------|
|`[Int32]`|false   |named   |False        |ConcurrentSendingDelayBeforeRetryingMinutes|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableLowFreeSpaceAlert**

Generate an alert when the free disk space on the site database server is low. Use the -FreeSpaceThresholdWarningGB and -FreeSpaceThresholdCriticalGB parameters to specify the specific thresholds.






|Type       |Required|Position|PipelineInput|Aliases                                          |
|-----------|--------|--------|-------------|-------------------------------------------------|
|`[Boolean]`|false   |named   |False        |GenerateAlertWhenFreeDiskSpaceOnSiteDatabaseIsLow|



#### **EnableWakeOnLan**

This parameter is for an earlier version of the feature. Instead, use the client settings for wake on LAN with the Set-CMClientSettingPowerManagement (Set-CMClientSettingPowerManagement.md)cmdlet.


For more information, see How to configure Wake on LAN in Configuration Manager (/mem/configmgr/core/clients/deploy/configure-wake-on-lan).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FreeSpaceThresholdCriticalGB**

When -EnableLowFreeSpaceAlert is `$true`, the site raises a critical alert when the free disk space falls below this value. Specify an integer for the free disk space in GB on the site database server.






|Type     |Required|Position|PipelineInput|Aliases                                                |
|---------|--------|--------|-------------|-------------------------------------------------------|
|`[Int32]`|false   |named   |False        |CriticalAlertWhenFreeDiskSpaceFallBelowFollowingValueGB|



#### **FreeSpaceThresholdWarningGB**

When -EnableLowFreeSpaceAlert is `$true`, the site raises a warning alert when the free disk space falls below this value. Specify an integer for the free disk space in GB on the site database server.






|Type     |Required|Position|PipelineInput|Aliases                                               |
|---------|--------|--------|-------------|------------------------------------------------------|
|`[Int32]`|false   |named   |False        |WarningAlertWhenFreeDiskSpaceFallBelowFollowingValueGB|



#### **InputObject**

Specifies a Configuration Manager site object to configure. To get a Configuration Manager site object, use the Get-CMSite (Get-CMSite.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **MaximumConcurrentSendingForAllSite**

A site can send data concurrently to multiple sites. This value specifies the maximum number of simultaneous communications to all sites. By default, the value is `5`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MaximumConcurrentSendingForPerSite**

A site can send data concurrently to multiple sites. This value specifies the maximum number of simultaneous communications to any single site. By default, the value is `3`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MaximumNumberOfSendingWakeupPacketBeforePausing**

This parameter is for an earlier version of the feature. Instead, use the client settings for wake on LAN with the Set-CMClientSettingPowerManagement (Set-CMClientSettingPowerManagement.md)cmdlet.


For more information, see How to configure Wake on LAN in Configuration Manager (/mem/configmgr/core/clients/deploy/configure-wake-on-lan).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Name**

Specifies the name of a Configuration Manager site to configure.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteName|



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PortForClientRequestServiceType**

When you use the -AddClientRequestServiceType parameter, use this parameter to specify a port number for client requests.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PromotePassiveSiteToActive**

Use this parameter to promote a site server in passive mode to the active site server. For more information, see Site server high availability in Configuration Manager (/mem/configmgr/core/servers/deploy/configure/site-server-high-availability).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveActiveDirectoryForest**

Specifies an array of Active Directory forest objects. When removed, this site doesn't publish to that forest.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **RemoveCertificateByKey**

Specifies an array of certificates to remove.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **RemoveClientRequestServiceType**

Specifies a service type to remove as a port that Configuration Manager uses to communicate with clients in this site.



Valid Values:

* WakeOnLanUdp
* ClientNotificationTcp
* ClientRequestHttpTcp
* ClientRequestsHttpsTcp
* ClientRequestHttpTcpDefault
* ClientRequestsHttpsTcpDefault






|Type                        |Required|Position|PipelineInput|
|----------------------------|--------|--------|-------------|
|`[ClientRequestServiceType]`|false   |named   |False        |



#### **RequireSha256**

When clients sign data and communicate with site systems by using HTTP, this option requires the clients to use SHA-256 to sign the data. Clients must support this hash algorithm. This option applies to clients that don't use PKI certificates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RequireSigning**

This option requires that clients sign data when they send to management points.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RetryInstallPassiveSite**

Use this parameter to retry the installation for a site server in passive mode that previously failed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RetryNumberForConcurrentSending**

A site can send data concurrently to multiple sites. If it needs to retry, this integer value specifies the number of times to retry a failed communication. By default, the value is `2`. Use the -ConcurrentSendingDelayBeforeRetryingMins parameter to specify the delay in minutes before it retries.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **RetryNumberOfSendingWakeupPacketTransmission**

This parameter is for an earlier version of the feature. Instead, use the client settings for wake on LAN with the Set-CMClientSettingPowerManagement (Set-CMClientSettingPowerManagement.md)cmdlet.


For more information, see How to configure Wake on LAN in Configuration Manager (/mem/configmgr/core/clients/deploy/configure-wake-on-lan).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SendingWakeupPacketBeforePausingWaitSec**

This parameter is for an earlier version of the feature. Instead, use the client settings for wake on LAN with the Set-CMClientSettingPowerManagement (Set-CMClientSettingPowerManagement.md)cmdlet.


For more information, see How to configure Wake on LAN in Configuration Manager (/mem/configmgr/core/clients/deploy/configure-wake-on-lan).






|Type     |Required|Position|PipelineInput|Aliases                                    |
|---------|--------|--------|-------------|-------------------------------------------|
|`[Int32]`|false   |named   |False        |SendingWakeupPacketBeforePausingWaitSeconds|



#### **SendingWakeupPacketTransmissionDelayMins**

This parameter is for an earlier version of the feature. Instead, use the client settings for wake on LAN with the Set-CMClientSettingPowerManagement (Set-CMClientSettingPowerManagement.md)cmdlet.


For more information, see How to configure Wake on LAN in Configuration Manager (/mem/configmgr/core/clients/deploy/configure-wake-on-lan).






|Type     |Required|Position|PipelineInput|Aliases                                    |
|---------|--------|--------|-------------|-------------------------------------------|
|`[Int32]`|false   |named   |False        |SendingWakeupPacketTransmissionDelayMinutes|



#### **SendingWakeupPacketTransmissionOffsetMins**

This parameter is for an earlier version of the feature. Instead, use the client settings for wake on LAN with the Set-CMClientSettingPowerManagement (Set-CMClientSettingPowerManagement.md)cmdlet.


For more information, see How to configure Wake on LAN in Configuration Manager (/mem/configmgr/core/clients/deploy/configure-wake-on-lan).






|Type     |Required|Position|PipelineInput|Aliases                                     |
|---------|--------|--------|-------------|--------------------------------------------|
|`[Int32]`|false   |named   |False        |SendingWakeupPacketTransmissionOffsetMinutes|



#### **SiteCode**

Specifies the Configuration Manager site code to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemCollectionBehavior**

For deployment verification (/mem/configmgr/core/servers/manage/settings-to-manage-high-risk-deployments), specify the behavior to take when the selected collection includes computers that host site systems roles.


* `Block`: Don't create the deployment


* `Warn`: Require verification before creating the deployment



Valid Values:

* Block
* Warn






|Type                      |Required|Position|PipelineInput|Aliases                                                 |
|--------------------------|--------|--------|-------------|--------------------------------------------------------|
|`[CollectionBehaviorType]`|false   |named   |False        |BehaviorWhenCollectionIncludesComputerHostSiteSystemRole|



#### **TakeActionForMultipleCertificateMatchCriteria**

Specifies the action to take if multiple certificates match criteria.



Valid Values:

* FailSelectionAndSendErrorMessage
* SelectCertificateWithLongestValidityPeriod






|Type                                             |Required|Position|PipelineInput|
|-------------------------------------------------|--------|--------|-------------|
|`[TakeActionForMultipleCertificateMatchCriteria]`|false   |named   |False        |



#### **ThreadNumberOfSendingWakeupPacket**

This parameter is for an earlier version of the feature. Instead, use the client settings for wake on LAN with the Set-CMClientSettingPowerManagement (Set-CMClientSettingPowerManagement.md)cmdlet.


For more information, see How to configure Wake on LAN in Configuration Manager (/mem/configmgr/core/clients/deploy/configure-wake-on-lan).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ThresholdOfSelectCollectionByDefault**

For deployment verification (/mem/configmgr/core/servers/manage/settings-to-manage-high-risk-deployments), configure the default collection size limit. The Select Collection window hides collections with membership that exceeds this default value. Specify `0` to disable.






|Type     |Required|Position|PipelineInput|Aliases                                 |
|---------|--------|--------|-------------|----------------------------------------|
|`[Int32]`|false   |named   |False        |SizeOfCustomCollectionCanSelectByDefault|



#### **ThresholdOfSelectCollectionMax**

For deployment verification (/mem/configmgr/core/servers/manage/settings-to-manage-high-risk-deployments), configure the maximum collection size limit. The Select Collection window always hides collections that have more members than this maximum size. Specify `0` to disable.






|Type     |Required|Position|PipelineInput|Aliases                               |
|---------|--------|--------|-------------|--------------------------------------|
|`[Int32]`|false   |named   |False        |SizeOfCustomCollectionCanSelectMaximum|



#### **UseCustomWebsite**

Indicates whether to use a custom web site. By default, Configuration Manager site system servers that require IIS to communicate with clients use the default web site.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseEncryption**

Enable this option to use 3DES to encrypt the client inventory data and state messages that are sent to the management point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UsePkiClientCertificate**

Indicates whether to use a PKI client certificate for client authentication when available.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseSmsGeneratedCert**

Use this parameter to enable or disable the site property to Use Configuration Manager-generated certificates for HTTP site systems . For more information, see Enhanced HTTP (/mem/configmgr/core/plan-design/hierarchy/enhanced-http).






|Type       |Required|Position|PipelineInput|Aliases                                           |
|-----------|--------|--------|-------------|--------------------------------------------------|
|`[Boolean]`|false   |named   |False        |UseConfigurationManagerGeneratedCertificateForHttp|



#### **WakeOnLanTransmissionMethodType**

Specifies the type of transmission method to use for Wake On LAN transmissions.



Valid Values:

* Unicast
* SubnetDirectedBroadcasts






|Type                               |Required|Position|PipelineInput|
|-----------------------------------|--------|--------|-------------|
|`[WakeOnLanTransmissionMethodType]`|false   |named   |False        |



#### **WakeOnLanType**

This parameter is for an earlier version of the feature. Instead, use the client settings for wake on LAN with the Set-CMClientSettingPowerManagement (Set-CMClientSettingPowerManagement.md)cmdlet.


For more information, see How to configure Wake on LAN in Configuration Manager (/mem/configmgr/core/clients/deploy/configure-wake-on-lan).



Valid Values:

* UseAmtPowerOnCommandsOrWakeupPackets
* UseAmtPowerOnCommandsOnly
* UseWakeupPacketsOnly






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[WakeOnLanType]`|false   |named   |False        |



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
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMSite [-AddActiveDirectoryForest <IResultObject[]>] [-AddCertificateByPath <String[]>] [-AddClientRequestServiceType {WakeOnLanUdp | ClientNotificationTcp | ClientRequestHttpTcp | ClientRequestsHttpsTcp | ClientRequestHttpTcpDefault | ClientRequestsHttpsTcpDefault}] [-ClientCertificateCustomStoreName <String>] [-ClientCertificateSelectionCriteriaType {ClientAuthentication | CertificateSubjectContainsString | CertificateSubjectOrSanIncludesAttributes | CertificateSubjectOrSanIncludesAtrributes}] [-ClientCertificateSelectionCriteriaValue <String>] [-ClientCheckCertificateRevocationListForSiteSystem <Boolean>] [-ClientComputerCommunicationType {HttpsOnly | HttpsOrHttp}] [-Comment <String>] [-ConcurrentSendingDelayBeforeRetryingMins <Int32>] [-DisableWildcardHandling] [-EnableLowFreeSpaceAlert <Boolean>] [-EnableWakeOnLan <Boolean>] [-ForceWildcardHandling] [-FreeSpaceThresholdCriticalGB <Int32>] [-FreeSpaceThresholdWarningGB <Int32>] -InputObject <IResultObject> [-MaximumConcurrentSendingForAllSite <Int32>] [-MaximumConcurrentSendingForPerSite <Int32>] [-MaximumNumberOfSendingWakeupPacketBeforePausing <Int32>] [-PassThru] [-PortForClientRequestServiceType <Int32>] [-PromotePassiveSiteToActive] [-RemoveActiveDirectoryForest <IResultObject[]>] [-RemoveCertificateByKey <String[]>] [-RemoveClientRequestServiceType {WakeOnLanUdp | ClientNotificationTcp | ClientRequestHttpTcp | ClientRequestsHttpsTcp | ClientRequestHttpTcpDefault | ClientRequestsHttpsTcpDefault}] [-RequireSha256 <Boolean>] [-RequireSigning <Boolean>] [-RetryInstallPassiveSite] [-RetryNumberForConcurrentSending <Int32>] [-RetryNumberOfSendingWakeupPacketTransmission <Int32>] [-SendingWakeupPacketBeforePausingWaitSec <Int32>] [-SendingWakeupPacketTransmissionDelayMins <Int32>] [-SendingWakeupPacketTransmissionOffsetMins <Int32>] [-SiteSystemCollectionBehavior {Block | Warn}] [-TakeActionForMultipleCertificateMatchCriteria {FailSelectionAndSendErrorMessage | SelectCertificateWithLongestValidityPeriod}] [-ThreadNumberOfSendingWakeupPacket <Int32>] [-ThresholdOfSelectCollectionByDefault <Int32>] [-ThresholdOfSelectCollectionMax <Int32>] [-UseCustomWebsite <Boolean>] [-UseEncryption <Boolean>] [-UsePkiClientCertificate <Boolean>] [-UseSmsGeneratedCert <Boolean>] [-WakeOnLanTransmissionMethodType {Unicast | SubnetDirectedBroadcasts}] [-WakeOnLanType {UseAmtPowerOnCommandsOrWakeupPackets | UseAmtPowerOnCommandsOnly | UseWakeupPacketsOnly}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSite [-AddActiveDirectoryForest <IResultObject[]>] [-AddCertificateByPath <String[]>] [-AddClientRequestServiceType {WakeOnLanUdp | ClientNotificationTcp | ClientRequestHttpTcp | ClientRequestsHttpsTcp | ClientRequestHttpTcpDefault | ClientRequestsHttpsTcpDefault}] [-ClientCertificateCustomStoreName <String>] [-ClientCertificateSelectionCriteriaType {ClientAuthentication | CertificateSubjectContainsString | CertificateSubjectOrSanIncludesAttributes | CertificateSubjectOrSanIncludesAtrributes}] [-ClientCertificateSelectionCriteriaValue <String>] [-ClientCheckCertificateRevocationListForSiteSystem <Boolean>] [-ClientComputerCommunicationType {HttpsOnly | HttpsOrHttp}] [-Comment <String>] [-ConcurrentSendingDelayBeforeRetryingMins <Int32>] [-DisableWildcardHandling] [-EnableLowFreeSpaceAlert <Boolean>] [-EnableWakeOnLan <Boolean>] [-ForceWildcardHandling] [-FreeSpaceThresholdCriticalGB <Int32>] [-FreeSpaceThresholdWarningGB <Int32>] [-MaximumConcurrentSendingForAllSite <Int32>] [-MaximumConcurrentSendingForPerSite <Int32>] [-MaximumNumberOfSendingWakeupPacketBeforePausing <Int32>] -Name <String> [-PassThru] [-PortForClientRequestServiceType <Int32>] [-PromotePassiveSiteToActive] [-RemoveActiveDirectoryForest <IResultObject[]>] [-RemoveCertificateByKey <String[]>] [-RemoveClientRequestServiceType {WakeOnLanUdp | ClientNotificationTcp | ClientRequestHttpTcp | ClientRequestsHttpsTcp | ClientRequestHttpTcpDefault | ClientRequestsHttpsTcpDefault}] [-RequireSha256 <Boolean>] [-RequireSigning <Boolean>] [-RetryInstallPassiveSite] [-RetryNumberForConcurrentSending <Int32>] [-RetryNumberOfSendingWakeupPacketTransmission <Int32>] [-SendingWakeupPacketBeforePausingWaitSec <Int32>] [-SendingWakeupPacketTransmissionDelayMins <Int32>] [-SendingWakeupPacketTransmissionOffsetMins <Int32>] [-SiteSystemCollectionBehavior {Block | Warn}] [-TakeActionForMultipleCertificateMatchCriteria {FailSelectionAndSendErrorMessage | SelectCertificateWithLongestValidityPeriod}] [-ThreadNumberOfSendingWakeupPacket <Int32>] [-ThresholdOfSelectCollectionByDefault <Int32>] [-ThresholdOfSelectCollectionMax <Int32>] [-UseCustomWebsite <Boolean>] [-UseEncryption <Boolean>] [-UsePkiClientCertificate <Boolean>] [-UseSmsGeneratedCert <Boolean>] [-WakeOnLanTransmissionMethodType {Unicast | SubnetDirectedBroadcasts}] [-WakeOnLanType {UseAmtPowerOnCommandsOrWakeupPackets | UseAmtPowerOnCommandsOnly | UseWakeupPacketsOnly}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSite [-AddActiveDirectoryForest <IResultObject[]>] [-AddCertificateByPath <String[]>] [-AddClientRequestServiceType {WakeOnLanUdp | ClientNotificationTcp | ClientRequestHttpTcp | ClientRequestsHttpsTcp | ClientRequestHttpTcpDefault | ClientRequestsHttpsTcpDefault}] [-ClientCertificateCustomStoreName <String>] [-ClientCertificateSelectionCriteriaType {ClientAuthentication | CertificateSubjectContainsString | CertificateSubjectOrSanIncludesAttributes | CertificateSubjectOrSanIncludesAtrributes}] [-ClientCertificateSelectionCriteriaValue <String>] [-ClientCheckCertificateRevocationListForSiteSystem <Boolean>] [-ClientComputerCommunicationType {HttpsOnly | HttpsOrHttp}] [-Comment <String>] [-ConcurrentSendingDelayBeforeRetryingMins <Int32>] [-DisableWildcardHandling] [-EnableLowFreeSpaceAlert <Boolean>] [-EnableWakeOnLan <Boolean>] [-ForceWildcardHandling] [-FreeSpaceThresholdCriticalGB <Int32>] [-FreeSpaceThresholdWarningGB <Int32>] [-MaximumConcurrentSendingForAllSite <Int32>] [-MaximumConcurrentSendingForPerSite <Int32>] [-MaximumNumberOfSendingWakeupPacketBeforePausing <Int32>] [-PassThru] [-PortForClientRequestServiceType <Int32>] [-PromotePassiveSiteToActive] [-RemoveActiveDirectoryForest <IResultObject[]>] [-RemoveCertificateByKey <String[]>] [-RemoveClientRequestServiceType {WakeOnLanUdp | ClientNotificationTcp | ClientRequestHttpTcp | ClientRequestsHttpsTcp | ClientRequestHttpTcpDefault | ClientRequestsHttpsTcpDefault}] [-RequireSha256 <Boolean>] [-RequireSigning <Boolean>] [-RetryInstallPassiveSite] [-RetryNumberForConcurrentSending <Int32>] [-RetryNumberOfSendingWakeupPacketTransmission <Int32>] [-SendingWakeupPacketBeforePausingWaitSec <Int32>] [-SendingWakeupPacketTransmissionDelayMins <Int32>] [-SendingWakeupPacketTransmissionOffsetMins <Int32>] [-SiteCode <String>] [-SiteSystemCollectionBehavior {Block | Warn}] [-TakeActionForMultipleCertificateMatchCriteria {FailSelectionAndSendErrorMessage | SelectCertificateWithLongestValidityPeriod}] [-ThreadNumberOfSendingWakeupPacket <Int32>] [-ThresholdOfSelectCollectionByDefault <Int32>] [-ThresholdOfSelectCollectionMax <Int32>] [-UseCustomWebsite <Boolean>] [-UseEncryption <Boolean>] [-UsePkiClientCertificate <Boolean>] [-UseSmsGeneratedCert <Boolean>] [-WakeOnLanTransmissionMethodType {Unicast | SubnetDirectedBroadcasts}] [-WakeOnLanType {UseAmtPowerOnCommandsOrWakeupPackets | UseAmtPowerOnCommandsOnly | UseWakeupPacketsOnly}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
