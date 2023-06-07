Get-CMSoftwareUpdate
--------------------




### Synopsis
Get a software update.



---


### Description

Use this cmdlet to get one or more software updates.



For more information, see Software update management documentation (/mem/configmgr/sum/)in the core docs.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateGroup](Get-CMSoftwareUpdateGroup)



* [Save-CMSoftwareUpdate](Save-CMSoftwareUpdate)



* [Set-CMSoftwareUpdate](Set-CMSoftwareUpdate)



* [Sync-CMSoftwareUpdate](Sync-CMSoftwareUpdate)



* [Get-CMSoftwareUpdateCategory](Get-CMSoftwareUpdateCategory)



* [Get-CMSoftwareUpdateGroup](Get-CMSoftwareUpdateGroup)



* [Get-CMSoftwareUpdateContentInfo](Get-CMSoftwareUpdateContentInfo)





---


### Examples
#### Example 1: Get downloaded software updates
```PowerShell
Get-CMSoftwareUpdate -IsContentProvisioned $True
```

#### Example 2: Get software updates by update group
```PowerShell
Get-CMSoftwareUpdateGroup -Name "TestSUgroup10" | Get-CMSoftwareUpdate
```



---


### Parameters
#### **ArticleId**

Specify the Article ID of a software update. For example, `4571687`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **BulletinId**

Specify the Bulletin ID of a software update. For example, `MS18-952`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Category**

Specify the category of a software update. To get a category object, use the Get-CMSoftwareUpdateCategory (Get-CMSoftwareUpdateCategory.md)cmdlet.






|Type               |Required|Position|PipelineInput |
|-------------------|--------|--------|--------------|
|`[IResultObject[]]`|false   |named   |True (ByValue)|



#### **CategoryName**

Specify an array of category names for software updates.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |CategoryNames|



#### **DatePostedMax**

Specify the latest date that a software update was released.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DatePostedMin**

Specify the earliest date that a software update was released.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DateRevisedMax**

Specify the latest date that a software update was revised.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DateRevisedMin**

Specify the earliest date that a software update was revised.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EulaExist**

Set this parameter to `$true` to filter results for all updates that have a license agreement.






|Type       |Required|Position|PipelineInput|Aliases   |
|-----------|--------|--------|-------------|----------|
|`[Boolean]`|false   |named   |False        |EulaExists|



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the ID of a software update. This value is the CI_ID , for example `143404`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **IncludeUpgrade**

Add this parameter to include software updates in the upgrade category.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|false   |named   |False        |IncludeUpgrades|



#### **IsContentProvisioned**

Set this parameter to `$true` to filter results for all updates for which the site has downloaded content.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsDeployed**

Set this parameter to `$true` to filter results for all updates that are deployed.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsExpired**

Set this parameter to `$true` to filter results for all updates that are expired.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsLatest**

Set this parameter to `$true` to filter results for the latest version of the software update.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsOfflineServiceable**

Set this parameter to `$true` to filter results for all updates that are offline-serviceable. You can use the DISM command-line tool to inject these updates into an OS image.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsSuperseded**

Set this parameter to `$true` to filter results for all updates that are superseded.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsUserDefined**

Set this parameter to `$true` to filter results for all updates that are user-defined.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify the name of a software update. This parameter compares against the localized display name attribute.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDisplayName|



#### **OnlyExpired**

Add this parameter to only search for expired software updates.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Severity**

Specify the severity of the software update.



Valid Values:

* None
* Low
* Moderate
* Important
* Critical






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[CustomSeverityType]`|false   |named   |False        |



#### **UpdateGroup**

Specify software update group object. To get this object, use the Get-CMSoftwareUpdateGroup (Get-CMSoftwareUpdateGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **UpdateGroupId**

Specify an array of IDs of software update groups. This value is the CI_ID or Config Item ID of the software update group. For example, `107078`.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **UpdateGroupName**

Specify an array of names of software update groups.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **Vendor**

Applies to version 2010 and later. Specify the name of the software update vendor. The vendor for most software updates is `"Microsoft"`. If you configure third-party software updates, use this value to filter on other update vendors.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]



Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_SoftwareUpdate


* IResultObject#SMS_SoftwareUpdate






---


### Notes
For more information on this return object and its properties, see SMS_SoftwareUpdate server WMI class (/mem/configmgr/develop/reference/sum/sms_softwareupdate-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMSoftwareUpdate [-ArticleId <String>] [-BulletinId <String>] [-Category <IResultObject[]>] [-CategoryName <String[]>] [-DatePostedMax <DateTime>] [-DatePostedMin <DateTime>] [-DateRevisedMax <DateTime>] [-DateRevisedMin <DateTime>] [-DisableWildcardHandling] [-EulaExist <Boolean>] [-Fast] [-ForceWildcardHandling] [-IncludeUpgrade] [-IsContentProvisioned <Boolean>] [-IsDeployed <Boolean>] [-IsExpired <Boolean>] [-IsLatest <Boolean>] [-IsOfflineServiceable <Boolean>] [-IsSuperseded <Boolean>] [-IsUserDefined <Boolean>] [-Name <String>] [-OnlyExpired] [-Severity {None | Low | Moderate | Important | Critical}] [-Vendor <String>] [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdate [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -Id <Int32> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdate [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -UpdateGroup <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdate [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -UpdateGroupId <String[]> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdate [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -UpdateGroupName <String[]> [<CommonParameters>]
```
