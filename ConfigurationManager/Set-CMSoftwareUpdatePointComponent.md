Set-CMSoftwareUpdatePointComponent
----------------------------------




### Synopsis
Configure the site component for the software update point.



---


### Description

Use this cmdlet to configure the site component for the software update point. Use it after you add a software update point, for example with the Add-CMSoftwareUpdatePoint cmdlet. You can also use this cmdlet to reconfigure an existing software update point.



A software update point component interacts with a Windows Server Update Services (WSUS) server to configure update settings, request synchronization to the upstream update source, and synchronize updates from the WSUS database to the site server database on the central site.



For more information, see Site components for Configuration Manager (/mem/configmgr/core/servers/deploy/configure/site-components).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdatePointComponent](Get-CMSoftwareUpdatePointComponent)



* [Add-CMSoftwareUpdatePoint](Add-CMSoftwareUpdatePoint)



* [Site components for Configuration Manager](Site components for Configuration Manager)





---


### Examples
#### Example 1: Modify a software update point site component
```PowerShell
$supComp = Get-CMSoftwareUpdatePointComponent -SiteSystemServerName 'sup1.contoso.com' -SiteCode 'XYZ'

$schedule = New-CMSchedule -RecurCount 3 -RecurInterval Days -Start "2020/1/7 12:00:00"

$addLang = "Dutch"
$removeLang = "English"

$parameters = @{
  InputObject = $supComp
  DefaultWsusServer = 'sup.contoso.com'
  SynchronizeAction = 'SynchronizeFromMicrosoftUpdate'
  ReportingEvent = 'CreateAllWsusReportingEvents'
  RemoveUpdateClassification = "Update Rollups"
  AddUpdateClassification = "Critical Updates"
  Schedule = $schedule
  EnableSyncFailureAlert = $true
  ImmediatelyExpireSupersedence = $true
  AddLanguageUpdateFile = $addLang
  AddLanguageSummaryDetails = $addLang
  RemoveLanguageUpdateFile = $removeLang
  RemoveLanguageSummaryDetails = $removeLang
}

Set-CMSoftwareUpdatePointComponent @parameters
```

#### Example 2: Disable software update point synchronization
```PowerShell
Set-CMSoftwareUpdatePointComponent -Name "Contoso-SiteSysSrv.Western.Contoso.com" -Schedule $null
```



---


### Parameters
#### **AddCompany**

This parameter is a string array of company names. Use this option to synchronize the entire company's list of Products .


To remove an entire company from this list, use the RemoveCompany parameter.


For more information, see Configure classifications and products to synchronize (/mem/configmgr/sum/get-started/configure-classifications-and-products).






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|false   |named   |False        |AddCompanies|



#### **AddLanguageSummaryDetail**

This parameter is a string array of language names. Use this option to download Summary details for the specified languages.


To remove languages from this list, use the RemoveLanguageSummaryDetail parameter.


For more information, see Plan for synchronization settings - Languages (/mem/configmgr/sum/plan-design/plan-for-software-updates#BKMK_UpdateLanguages).






|Type        |Required|Position|PipelineInput|Aliases                  |
|------------|--------|--------|-------------|-------------------------|
|`[String[]]`|false   |named   |False        |AddLanguageSummaryDetails|



#### **AddLanguageUpdateFile**

This parameter is a string array of language names. Use this option to download the Software update file for the specified languages.


To remove languages from this list, use the RemoveLanguageUpdateFile parameter.


For more information, see Plan for synchronization settings - Languages (/mem/configmgr/sum/plan-design/plan-for-software-updates#BKMK_UpdateLanguages).






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **AddProduct**

This parameter is a string array of product names. Use this option to synchronize Products .


To remove a product from this list, use the RemoveProduct parameter.


For more information, see Configure classifications and products to synchronize (/mem/configmgr/sum/get-started/configure-classifications-and-products).






|Type        |Required|Position|PipelineInput|Aliases    |
|------------|--------|--------|-------------|-----------|
|`[String[]]`|false   |named   |False        |AddProducts|



#### **AddProductFamily**

This parameter is a string array of product family names. Use this option to synchronize a product family's list of Products .


To remove an entire product family from this list, use the RemoveProductFamily parameter.


For more information, see Configure classifications and products to synchronize (/mem/configmgr/sum/get-started/configure-classifications-and-products).






|Type        |Required|Position|PipelineInput|Aliases           |
|------------|--------|--------|-------------|------------------|
|`[String[]]`|false   |named   |False        |AddProductFamilies|



#### **AddUpdateClassification**

This parameter is a string array of update classifications. Use this option to synchronize specific software update Classifications .


To remove a classification from this list, use the RemoveUpdateClassification parameter.


For more information, see Configure classifications and products to synchronize (/mem/configmgr/sum/get-started/configure-classifications-and-products).






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **ContentFileOption**

Use this parameter to configure how the software update point downloads update files. Express installation files provide smaller download and faster installation on computers because only the necessary files are downloaded and installed. They're larger files and will increase download times for your site servers and distribution points.


* `FullFilesOnly`: Download full files for all approved updates


* `ExpressForWindows10Only`: Download both full files for all approved updates and express installation files for Windows 10 or later



Valid Values:

* FullFilesOnly
* ExpressForWindows10Only






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[ContentFileOptions]`|false   |named   |False        |



#### **DefaultWsusServer**

Specify the FQDN of the WSUS server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableCallWsusCleanupWizard**

Set this parameter to `$true` to enable WSUS cleanup tasks to run after synchronization. For more information, see Software updates maintenance (/mem/configmgr/sum/deploy-use/software-updates-maintenance).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableManualCertManagement**

Set this parameter to `$true` to manually manage the WSUS signing certificate for third-party updates. This parameter is dependent on the EnableThirdPartyUpdates parameter.


For more information, see Enable third-party updates (/mem/configmgr/sum/deploy-use/third-party-software-updates).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSyncFailureAlert**

Set this parameter to `$true` to enable the component to create an alert when synchronization fails.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableThirdPartyUpdates**

Set this parameter to `$true` to Enable third-party software updates . You can also use the EnableManualCertManagement parameter.


For more information, see Enable third-party updates (/mem/configmgr/sum/deploy-use/third-party-software-updates).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **FeatureUpdateMaxRuntimeMins**

Specify an integer value for the default maximum amount of time a software update installation has to complete. You can override this default for a specific update. This setting only affects newly synchronized updates. This parameter only applies to Windows feature updates.


To configure the maximum run time for Office 365 updates and non-feature updates for Windows, use the NonFeatureUpdateMaxRuntimeMins parameter.


For more information, see Plan for synchronization settings (/mem/configmgr/sum/plan-design/plan-for-software-updates#bkmk_maxruntime).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ImmediatelyExpireSupersedence**

Set this parameter to `$true` to immediately expire a software update when another update supersedes it or after a specified period of time.


If you specify a value of `$False` for this parameter, specify the number of months to wait for expiration by using the WaitMonth parameter.


Some updates never expire, for example definition updates.


If you change this setting, the site starts a full synchronization.


To configure this behavior for Windows feature updates, use the ImmediatelyExpireSupersedenceForFeature parameter.






|Type       |Required|Position|PipelineInput|Aliases                                   |
|-----------|--------|--------|-------------|------------------------------------------|
|`[Boolean]`|false   |named   |False        |ImmediatelyExpireSupersedenceForNonFeature|



#### **ImmediatelyExpireSupersedenceForFeature**

Set this parameter to `$true` to immediately expire a Windows feature update when another update supersedes it or after a specified period of time.


If you specify a value of `$False` for this parameter, specify the number of months to wait for expiration by using the WaitMonthForFeature parameter.


If you change this setting, the site starts a full synchronization.


To configure this behavior for non-feature updates, use the ImmediatelyExpireSupersedence parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**

Specify a software update point site component object to configure. To get this object, use the Get-CMSoftwareUpdatePointComponent (Get-CMSoftwareUpdatePointComponent.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases               |
|-----------------|--------|--------|--------------|----------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Site<br/>SiteComponent|



#### **Name**

Specify the name of a site system server with the software update point role.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteName|



#### **NonFeatureUpdateMaxRuntimeMins**

Specify an integer value for the default maximum amount of time a software update installation has to complete. You can override this default for a specific update. This setting only affects newly synchronized updates. This parameter only applies to Office 365 updates and non-feature updates for Windows.


To configure the maximum run time for Windows feature updates, use the FeatureUpdateMaxRuntimeMins parameter.


For more information, see Plan for synchronization settings (/mem/configmgr/sum/plan-design/plan-for-software-updates#bkmk_maxruntime).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveCompany**

This parameter is a string array of company names. Use this option to not synchronize the entire company's list of Products .


To add an entire company to this list, use the AddCompany parameter.


For more information, see Configure classifications and products to synchronize (/mem/configmgr/sum/get-started/configure-classifications-and-products).






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|false   |named   |False        |RemoveCompanies|



#### **RemoveLanguageSummaryDetail**

This parameter is a string array of language names. Use this option to not download Summary details for the specified languages.


To add languages to this list, use the AddLanguageSummaryDetail parameter.


For more information, see Plan for synchronization settings - Languages (/mem/configmgr/sum/plan-design/plan-for-software-updates#BKMK_UpdateLanguages).






|Type        |Required|Position|PipelineInput|Aliases                     |
|------------|--------|--------|-------------|----------------------------|
|`[String[]]`|false   |named   |False        |RemoveLanguageSummaryDetails|



#### **RemoveLanguageUpdateFile**

This parameter is a string array of language names. Use this option to not download the Software update file for the specified languages.


To add languages to this list, use the AddLanguageUpdateFile parameter.


For more information, see Plan for synchronization settings - Languages (/mem/configmgr/sum/plan-design/plan-for-software-updates#BKMK_UpdateLanguages).






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **RemoveProduct**

This parameter is a string array of product names. Use this option to not synchronize Products .


To add a product to this list, use the AddProduct parameter.


For more information, see Configure classifications and products to synchronize (/mem/configmgr/sum/get-started/configure-classifications-and-products).






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|false   |named   |False        |RemoveProducts|



#### **RemoveProductFamily**

This parameter is a string array of product family names. Use this option to not synchronize a product family's list of Products .


To add an entire product family to this list, use the AddProductFamily parameter.


For more information, see Configure classifications and products to synchronize (/mem/configmgr/sum/get-started/configure-classifications-and-products).






|Type        |Required|Position|PipelineInput|Aliases              |
|------------|--------|--------|-------------|---------------------|
|`[String[]]`|false   |named   |False        |RemoveProductFamilies|



#### **RemoveUpdateClassification**

This parameter is a string array of update classifications. Use this option to not synchronize specific software update Classifications .


To add a classification to this list, use the AddUpdateClassification parameter.


For more information, see Configure classifications and products to synchronize (/mem/configmgr/sum/get-started/configure-classifications-and-products).






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **ReportingEvent**

Specify whether the Windows Update Agent (WUA) on clients create event messages for WSUS reporting. Configuration Manager doesn't use these events. Don't create these events, unless you require them for other uses.



Valid Values:

* DoNotCreateWsusReportingEvents
* CreateOnlyWsusStatusReportingEvents
* CreateAllWsusReportingEvents






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[ReportingEventType]`|false   |named   |False        |



#### **Schedule**

Specify a Schedule object to enable synchronization. To disable synchronization, set this parameter to `$null`.


To get a schedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **SiteCode**

Specify the three-character code for the site at which to configure its software update point component.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SynchronizeAction**

Specify the synchronization source for this software update point.


If you select a value of `SynchronizeFromAnUpstreamDataSourceLocation`, specify the data source location by using the UpstreamSourceLocation parameter.


For more information, see Plan for synchronization settings (/mem/configmgr/sum/plan-design/plan-for-software-updates#BKMK_SyncSource).



Valid Values:

* SynchronizeFromMicrosoftUpdate
* SynchronizeFromAnUpstreamDataSourceLocation
* DoNotSynchronizeFromMicrosoftUpdateOrUpstreamDataSource






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[SynchronizeActionType]`|false   |named   |False        |



#### **UpstreamSourceLocation**

Specify an upstream data location as a URL. For example, `https://wsusserver.contoso.com:8531`


To use this location, specify `SynchronizeFromAnUpstreamDataSourceLocation` for the SynchronizeAction parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **WaitMonth**

Set the integer value for the number of months to wait before a software update expires after another update supersedes it.


This parameter depends on the ImmediatelyExpireSupersedence parameter.






|Type     |Required|Position|PipelineInput|Aliases               |
|---------|--------|--------|-------------|----------------------|
|`[Int32]`|false   |named   |False        |WaitMonthForNonFeature|



#### **WaitMonthForFeature**

Set the integer value for the number of months to wait before a Windows feature update expires after another update supersedes it.


This parameter depends on the ImmediatelyExpireSupersedenceForFeature parameter.






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





---


### Outputs
* IResultObject#SMS_SCI_Component






---


### Notes
For more information on this return object and its properties, see SMS_SCI_Component server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_sci_component-server-wmi-class).



---


### Syntax
```PowerShell
Set-CMSoftwareUpdatePointComponent [-AddCompany <String[]>] [-AddLanguageSummaryDetail <String[]>] [-AddLanguageUpdateFile <String[]>] [-AddProduct <String[]>] [-AddProductFamily <String[]>] [-AddUpdateClassification <String[]>] [-ContentFileOption {FullFilesOnly | ExpressForWindows10Only}] [-DefaultWsusServer <String>] [-DisableWildcardHandling] [-EnableCallWsusCleanupWizard <Boolean>] [-EnableManualCertManagement <Boolean>] [-EnableSyncFailureAlert <Boolean>] [-EnableThirdPartyUpdates <Boolean>] [-FeatureUpdateMaxRuntimeMins <Int32>] [-ForceWildcardHandling] [-ImmediatelyExpireSupersedence <Boolean>] [-ImmediatelyExpireSupersedenceForFeature <Boolean>] -InputObject <IResultObject> [-NonFeatureUpdateMaxRuntimeMins <Int32>] [-PassThru] [-RemoveCompany <String[]>] [-RemoveLanguageSummaryDetail <String[]>] [-RemoveLanguageUpdateFile <String[]>] [-RemoveProduct <String[]>] [-RemoveProductFamily <String[]>] [-RemoveUpdateClassification <String[]>] [-ReportingEvent {DoNotCreateWsusReportingEvents | CreateOnlyWsusStatusReportingEvents | CreateAllWsusReportingEvents}] [-Schedule <IResultObject>] [-SynchronizeAction {SynchronizeFromMicrosoftUpdate | SynchronizeFromAnUpstreamDataSourceLocation | DoNotSynchronizeFromMicrosoftUpdateOrUpstreamDataSource}] [-UpstreamSourceLocation <String>] [-WaitMonth <Int32>] [-WaitMonthForFeature <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdatePointComponent [-AddCompany <String[]>] [-AddLanguageSummaryDetail <String[]>] [-AddLanguageUpdateFile <String[]>] [-AddProduct <String[]>] [-AddProductFamily <String[]>] [-AddUpdateClassification <String[]>] [-ContentFileOption {FullFilesOnly | ExpressForWindows10Only}] [-DefaultWsusServer <String>] [-DisableWildcardHandling] [-EnableCallWsusCleanupWizard <Boolean>] [-EnableManualCertManagement <Boolean>] [-EnableSyncFailureAlert <Boolean>] [-EnableThirdPartyUpdates <Boolean>] [-FeatureUpdateMaxRuntimeMins <Int32>] [-ForceWildcardHandling] [-ImmediatelyExpireSupersedence <Boolean>] [-ImmediatelyExpireSupersedenceForFeature <Boolean>] -Name <String> [-NonFeatureUpdateMaxRuntimeMins <Int32>] [-PassThru] [-RemoveCompany <String[]>] [-RemoveLanguageSummaryDetail <String[]>] [-RemoveLanguageUpdateFile <String[]>] [-RemoveProduct <String[]>] [-RemoveProductFamily <String[]>] [-RemoveUpdateClassification <String[]>] [-ReportingEvent {DoNotCreateWsusReportingEvents | CreateOnlyWsusStatusReportingEvents | CreateAllWsusReportingEvents}] [-Schedule <IResultObject>] [-SynchronizeAction {SynchronizeFromMicrosoftUpdate | SynchronizeFromAnUpstreamDataSourceLocation | DoNotSynchronizeFromMicrosoftUpdateOrUpstreamDataSource}] [-UpstreamSourceLocation <String>] [-WaitMonth <Int32>] [-WaitMonthForFeature <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdatePointComponent [-AddCompany <String[]>] [-AddLanguageSummaryDetail <String[]>] [-AddLanguageUpdateFile <String[]>] [-AddProduct <String[]>] [-AddProductFamily <String[]>] [-AddUpdateClassification <String[]>] [-ContentFileOption {FullFilesOnly | ExpressForWindows10Only}] [-DefaultWsusServer <String>] [-DisableWildcardHandling] [-EnableCallWsusCleanupWizard <Boolean>] [-EnableManualCertManagement <Boolean>] [-EnableSyncFailureAlert <Boolean>] [-EnableThirdPartyUpdates <Boolean>] [-FeatureUpdateMaxRuntimeMins <Int32>] [-ForceWildcardHandling] [-ImmediatelyExpireSupersedence <Boolean>] [-ImmediatelyExpireSupersedenceForFeature <Boolean>] [-NonFeatureUpdateMaxRuntimeMins <Int32>] [-PassThru] [-RemoveCompany <String[]>] [-RemoveLanguageSummaryDetail <String[]>] [-RemoveLanguageUpdateFile <String[]>] [-RemoveProduct <String[]>] [-RemoveProductFamily <String[]>] [-RemoveUpdateClassification <String[]>] [-ReportingEvent {DoNotCreateWsusReportingEvents | CreateOnlyWsusStatusReportingEvents | CreateAllWsusReportingEvents}] [-Schedule <IResultObject>] [-SiteCode <String>] [-SynchronizeAction {SynchronizeFromMicrosoftUpdate | SynchronizeFromAnUpstreamDataSourceLocation | DoNotSynchronizeFromMicrosoftUpdateOrUpstreamDataSource}] [-UpstreamSourceLocation <String>] [-WaitMonth <Int32>] [-WaitMonthForFeature <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
