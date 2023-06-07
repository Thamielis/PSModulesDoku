Set-CMApplication
-----------------




### Synopsis
Configure the properties of an application.



---


### Description

Use the Set-CMApplication cmdlet to configure the settings of an application.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Convert-CMApplication](Convert-CMApplication)



* [ConvertFrom-CMApplication](ConvertFrom-CMApplication)



* [ConvertTo-CMApplication](ConvertTo-CMApplication)



* [Export-CMApplication](Export-CMApplication)



* [Get-CMApplication](Get-CMApplication)



* [Import-CMApplication](Import-CMApplication)



* [New-CMApplication](New-CMApplication)



* [Remove-CMApplication](Remove-CMApplication)



* [Resume-CMApplication](Resume-CMApplication)



* [Suspend-CMApplication](Suspend-CMApplication)



* [New-CMApplicationDisplayInfo](New-CMApplicationDisplayInfo)



* [Create applications in Configuration Manager](Create applications in Configuration Manager)





---


### Examples
#### Example 1: Reconfigure the properties of an application
```PowerShell
$app = Get-CMApplication -Name "Application01"
$userCat = Get-CMCategory -Name "Test Applications" -CategoryType CatalogCategories
$adminCat = Get-CMCategory -Name "Testing" -CategoryType AppCategories

Set-CMApplication -InputObject $app -NewName "Application01_New" -Description "Application updated" -Publisher "Test group" -SoftwareVersion "1.0.0.1" -OptionalReference "Reference" -ReleaseDate 2/24/2016 -AutoInstall $True -Owner "jqpublic" -SupportContact "jqpublic" -LocalizedApplicationName "Localized Application01" -UserDocumentation "https://contoso.com/content" -LinkText "For more info" -LocalizedDescription "Localized Application New" -Keyword "Application" -PrivacyUrl "https://contoso.com/privacy" -IsFeatured $True -IconLocationFile "C:\Users\art\icon.png" -DistributionPriority Medium -SendToProtectedDistributionPoint $True -DistributionPointSetting NoDownload -AddUserCategory $userCat -AddAppCategory $adminCat
```



---


### Parameters
#### **AddAppCatalog**

Use this parameter to specify a Software Center entry for a specific language. This entry can include all of the localized information about the app:


* Description


* IconLocationFile


* Keyword


* LinkText


* PrivacyUrl


* Title


* UserDocumentation




To get this object, use the New-CMApplicationDisplayInfo (New-CMApplicationDisplayInfo.md)cmdlet.







|Type                |Required|Position|PipelineInput|Aliases    |
|--------------------|--------|--------|-------------|-----------|
|`[AppDisplayInfo[]]`|false   |named   |False        |AppCatalogs|



#### **AddAppCategory**

Specify one or more administrative category objects to help you filter and find the app in the console. To get these objects, use the Get-CMCategory (Get-CMCategory.md)cmdlet. These categories are of type AppCategories .


To add categories to help users filter and find applications in Software Center, use the AddUserCategory parameter.






|Type               |Required|Position|PipelineInput|Aliases         |
|-------------------|--------|--------|-------------|----------------|
|`[IResultObject[]]`|false   |named   |False        |AddAppCategories|



#### **AddOwner**

Specify one or more administrative users who are responsible for this app.






|Type        |Required|Position|PipelineInput|Aliases  |
|------------|--------|--------|-------------|---------|
|`[String[]]`|false   |named   |False        |AddOwners|



#### **AddSupportContact**

Specify one or more administrative users that end users can contact for help with this application.






|Type        |Required|Position|PipelineInput|Aliases           |
|------------|--------|--------|-------------|------------------|
|`[String[]]`|false   |named   |False        |AddSupportContacts|



#### **AddUserCategory**

Specify one or more user category objects to help you filter and find the app group in the console. To get these objects, use the Get-CMCategory (Get-CMCategory.md)cmdlet. These categories are of type CatalogCategories .


To add categories to help users filter and find applications in Software Center, use the AddAppCategory parameter.






|Type               |Required|Position|PipelineInput|Aliases          |
|-------------------|--------|--------|-------------|-----------------|
|`[IResultObject[]]`|false   |named   |False        |AddUserCategories|



#### **AppCategory**

This parameter is deprecated, use -AddAppCategory .






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |AppCategories|



#### **ApplyToLanguageById**

For settings that display in Software Center, use this parameter to specify the language ID for the settings.


This ID is the decimal equivalent of the Windows language ID. For example, `1033` is `0x0409` for English (United States) , and `2108` is `0x083C` for Irish (Ireland) . For more information, see [MS-LCID]: Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).


For example, to add a localized app name for Irish (Ireland) :


`-ApplyToLanguageById 2108 -LocalizedName "Fáilte romhat"`






|Type     |Required|Position|PipelineInput|Aliases                       |
|---------|--------|--------|-------------|------------------------------|
|`[Int32]`|false   |named   |False        |ApplySettingToSpecificLanguage|



#### **AutoInstall**

Set this parameter to $true to allow the app to be installed from the Install Application task sequence step without being deployed.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CleanAppCategory**

Add this parameter to remove all administrative categories. To remove a single category, use the RemoveAppCategory parameter.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Switch]`|false   |named   |False        |CleanAppCategories|



#### **CleanUserCategory**

Add this parameter to remove all user categories. To remove a single category, use the RemoveUserCategory parameter.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[Switch]`|false   |named   |False        |CleanUserCategories|



#### **ClearAppCatalog**

Add this parameter to remove all localized Software Center entries. To remove a single entry, use the RemoveAppCatalog parameter.






|Type      |Required|Position|PipelineInput|Aliases                                                  |
|----------|--------|--------|-------------|---------------------------------------------------------|
|`[Switch]`|false   |named   |False        |ClearAppCatalogs<br/>CleanAppCatalog<br/>CleanAppCatalogs|



#### **ClearOwner**

Add this parameter to remove all owners. To remove a single owner, use the RemoveOwner parameter.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[Switch]`|false   |named   |False        |CleanOwners|



#### **ClearSupportContact**

Add this parameter to remove all support contacts. To remove a single contact, use the RemoveSupportContact parameter.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[Switch]`|false   |named   |False        |CleanSupportContacts|



#### **DefaultLanguageId**

Specify the language ID for the default Software Center language.


This ID is the decimal equivalent of the Windows language ID. For example, `1033` is `0x0409` for English (United States) , and `2108` is `0x083C` for Irish (Ireland) . For more information, see [MS-LCID]: Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Description**

Specify an optional administrator comment for the app. The maximum length is 2048 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisplaySupersedenceInApplicationCatalog**

While the application catalog is no longer supported, you can still use this parameter to allow users to see in Software Center deployments for this application and all applications that it supersedes.






|Type       |Required|Position|PipelineInput|Aliases                                 |
|-----------|--------|--------|-------------|----------------------------------------|
|`[Boolean]`|false   |named   |False        |DisplaySupersedencesInApplicationCatalog|



#### **DistributionPointSetting**

Specify the prestaged distribution point settings:


* `AutoDownload`: Automatically download content when packages are assigned to distribution points.


* `DeltaCopy`: Download only content changes to distribution points.


* `NoDownload`: Manually copy the content in this package to distribution points.



Valid Values:

* AutoDownload
* DeltaCopy
* NoDownload






|Type                            |Required|Position|PipelineInput|
|--------------------------------|--------|--------|-------------|
|`[DistributionPointSettingType]`|false   |named   |False        |



#### **DistributionPriority**

Specify the order in which the site sends the content to other sites and the distribution points in this site.


The site sends high priority content before content with medium or low priority. Content with equal priority are sent in the order in which they're created.



Valid Values:

* Low
* Medium
* High






|Type                        |Required|Position|PipelineInput|
|----------------------------|--------|--------|-------------|
|`[DistributionPriorityType]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IconLocationFile**

Specify the path to the file that contains the icon for this app. Icons can have pixel dimensions of up to 512x512. The file can be of the following image and icon file types:


* DLL


* EXE


* JPG


* ICO


* PNG






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Id**

Specify the ID of the app to configure. This value is the same as the CI_ID , for example `1025866`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify an app object to configure. To get this object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |0       |True (ByValue)|Application|



#### **IsFeatured**

Set this parameter to $true to display this application as a featured app and highlight it in the Company Portal.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Keyword**

Specify a list of keywords in the selected language. These keywords help Software Center users search for the app group.


> [!TIP] > To add multiple keywords, use CultureInfo.CurrentCulture.TextInfo.ListSeparator as the delimiter.






|Type        |Required|Position|PipelineInput|Aliases |
|------------|--------|--------|-------------|--------|
|`[String[]]`|false   |named   |False        |Keywords|



#### **LinkText**

When you use the UserDocumentation parameter, use this parameter to show a string in place of "Additional information" in Software Center. The maximum length is 128 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **LocalizedApplicationName**

Specify the app name in the selected language. This name appears in Software Center.


A name is required for each language that you add.


The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **LocalizedDescription**

Specify a description for this app in the selected language. The maximum length is 2048 characters.






|Type      |Required|Position|PipelineInput|Aliases                        |
|----------|--------|--------|-------------|-------------------------------|
|`[String]`|false   |named   |False        |LocalizedApplicationDescription|



#### **ModelName**

Specify the application model identifier of the app to configure. This value is also known as the CI Unique ID . For example, `ScopeId_0D7D8B60-F2F9-484A-B9F3-4A8B68D14D59/ApplicationGroup_047fbf05-55f4-42ab-9581-e63fd0337fed`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Name**

Specify the name of the app to configure.






|Type      |Required|Position|PipelineInput|Aliases                                 |
|----------|--------|--------|-------------|----------------------------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName<br/>ApplicationName|



#### **NewName**

Use this parameter to rename the app. The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OptionalReference**

Specify an optional string to help you find the app in the console. The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Owner**

Specify an administrative user who's responsible for this app.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PrivacyUrl**

Specify a website address to the privacy statement for the app. The format needs to be a valid URL, for example `https://contoso.com/privacy`. The maximum length of the entire string is 128 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Publisher**

Specify optional vendor information for this app. The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |Manufacturer|



#### **ReleaseDate**

Specify a date object for when this app was released. To get this object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)built-in cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **RemoveAppCatalog**

Specify an array of language IDs to remove the associated Software Center entries. To remove all entries, use the ClearAppCatalog parameter.


This ID is the decimal equivalent of the Windows language ID. For example, `1033` is `0x0409` for English (United States) , and `2108` is `0x083C` for Irish (Ireland) . For more information, see [MS-LCID]: Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).


For example, to remove the localized Software Center entry for Irish (Ireland) :


`-RemoveAppCatalog 2108`






|Type       |Required|Position|PipelineInput|Aliases                      |
|-----------|--------|--------|-------------|-----------------------------|
|`[Int32[]]`|false   |named   |False        |RemoveAppCatalogsByLanguageId|



#### **RemoveAppCategoryName**

Specify an array of administrative category names to remove. To remove all administrative categories, use the CleanAppCategory parameter.






|Type        |Required|Position|PipelineInput|Aliases               |
|------------|--------|--------|-------------|----------------------|
|`[String[]]`|false   |named   |False        |RemoveAppCategoryNames|



#### **RemoveOwner**

Specify an array of owners to remove. To remove all owners, use the ClearOwner parameter.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|false   |named   |False        |RemoveOwners|



#### **RemoveSupportContact**

Specify an array of support contacts to remove. To remove all support contacts, use the ClearSupportContact parameter.






|Type        |Required|Position|PipelineInput|Aliases              |
|------------|--------|--------|-------------|---------------------|
|`[String[]]`|false   |named   |False        |RemoveSupportContacts|



#### **RemoveUserCategoryName**

Specify an array of user category names to remove. To remove all user categories, use the CleanUserCategory parameter.






|Type        |Required|Position|PipelineInput|Aliases                |
|------------|--------|--------|-------------|-----------------------|
|`[String[]]`|false   |named   |False        |RemoveUserCategoryNames|



#### **SendToProtectedDistributionPoint**

Indicates whether to copy this application to protected distribution points.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SoftwareVersion**

Specify an optional version string for the app. The maximum length is 64 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SupportContact**

Specify an administrative user that end users can contact for help with this application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserCategory**

This parameter is deprecated, use -AddUserCategory .






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|false   |named   |False        |UserCategories|



#### **UserDocumentation**

Specify the location of a file from which Software Center users can get more information about this app. This location is a website address, or a network path and file name. Make sure that users have access to this location.


The maximum length of the entire string is 256 characters.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_Application






---


### Notes
For more information on this return object and its properties, see SMS_Application server WMI class (/mem/configmgr/develop/reference/apps/sms_application-server-wmi-class).



---


### Syntax
```PowerShell
Set-CMApplication [-Id] <Int32> [-AddAppCatalog <AppDisplayInfo[]>] [-AddAppCategory <IResultObject[]>] [-AddOwner <String[]>] [-AddSupportContact <String[]>] [-AddUserCategory <IResultObject[]>] [-AppCategory <String[]>] [-ApplyToLanguageById <Int32>] [-AutoInstall <Boolean>] [-CleanAppCategory] [-CleanUserCategory] [-ClearAppCatalog] [-ClearOwner] [-ClearSupportContact] [-DefaultLanguageId <Int32>] [-Description <String>] [-DisableWildcardHandling] [-DisplaySupersedenceInApplicationCatalog <Boolean>] [-DistributionPointSetting {AutoDownload | DeltaCopy | NoDownload}] [-DistributionPriority {High | Medium | Low}] [-ForceWildcardHandling] [-IconLocationFile <String>] [-IsFeatured <Boolean>] [-Keyword <String[]>] [-LinkText <String>] [-LocalizedApplicationName <String>] [-LocalizedDescription <String>] [-NewName <String>] [-OptionalReference <String>] [-Owner <String>] [-PassThru] [-PrivacyUrl <String>] [-Publisher <String>] [-ReleaseDate <DateTime>] [-RemoveAppCatalog <Int32[]>] [-RemoveAppCategoryName <String[]>] [-RemoveOwner <String[]>] [-RemoveSupportContact <String[]>] [-RemoveUserCategoryName <String[]>] [-SendToProtectedDistributionPoint <Boolean>] [-SoftwareVersion <String>] [-SupportContact <String>] [-UserCategory <String[]>] [-UserDocumentation <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplication [-InputObject] <IResultObject> [-AddAppCatalog <AppDisplayInfo[]>] [-AddAppCategory <IResultObject[]>] [-AddOwner <String[]>] [-AddSupportContact <String[]>] [-AddUserCategory <IResultObject[]>] [-AppCategory <String[]>] [-ApplyToLanguageById <Int32>] [-AutoInstall <Boolean>] [-CleanAppCategory] [-CleanUserCategory] [-ClearAppCatalog] [-ClearOwner] [-ClearSupportContact] [-DefaultLanguageId <Int32>] [-Description <String>] [-DisableWildcardHandling] [-DisplaySupersedenceInApplicationCatalog <Boolean>] [-DistributionPointSetting {AutoDownload | DeltaCopy | NoDownload}] [-DistributionPriority {High | Medium | Low}] [-ForceWildcardHandling] [-IconLocationFile <String>] [-IsFeatured <Boolean>] [-Keyword <String[]>] [-LinkText <String>] [-LocalizedApplicationName <String>] [-LocalizedDescription <String>] [-NewName <String>] [-OptionalReference <String>] [-Owner <String>] [-PassThru] [-PrivacyUrl <String>] [-Publisher <String>] [-ReleaseDate <DateTime>] [-RemoveAppCatalog <Int32[]>] [-RemoveAppCategoryName <String[]>] [-RemoveOwner <String[]>] [-RemoveSupportContact <String[]>] [-RemoveUserCategoryName <String[]>] [-SendToProtectedDistributionPoint <Boolean>] [-SoftwareVersion <String>] [-SupportContact <String>] [-UserCategory <String[]>] [-UserDocumentation <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplication [-AddAppCatalog <AppDisplayInfo[]>] [-AddAppCategory <IResultObject[]>] [-AddOwner <String[]>] [-AddSupportContact <String[]>] [-AddUserCategory <IResultObject[]>] [-AppCategory <String[]>] [-ApplyToLanguageById <Int32>] [-AutoInstall <Boolean>] [-CleanAppCategory] [-CleanUserCategory] [-ClearAppCatalog] [-ClearOwner] [-ClearSupportContact] [-DefaultLanguageId <Int32>] [-Description <String>] [-DisableWildcardHandling] [-DisplaySupersedenceInApplicationCatalog <Boolean>] [-DistributionPointSetting {AutoDownload | DeltaCopy | NoDownload}] [-DistributionPriority {High | Medium | Low}] [-ForceWildcardHandling] [-IconLocationFile <String>] [-IsFeatured <Boolean>] [-Keyword <String[]>] [-LinkText <String>] [-LocalizedApplicationName <String>] [-LocalizedDescription <String>] -ModelName <String> [-NewName <String>] [-OptionalReference <String>] [-Owner <String>] [-PassThru] [-PrivacyUrl <String>] [-Publisher <String>] [-ReleaseDate <DateTime>] [-RemoveAppCatalog <Int32[]>] [-RemoveAppCategoryName <String[]>] [-RemoveOwner <String[]>] [-RemoveSupportContact <String[]>] [-RemoveUserCategoryName <String[]>] [-SendToProtectedDistributionPoint <Boolean>] [-SoftwareVersion <String>] [-SupportContact <String>] [-UserCategory <String[]>] [-UserDocumentation <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplication [-Name] <String> [-AddAppCatalog <AppDisplayInfo[]>] [-AddAppCategory <IResultObject[]>] [-AddOwner <String[]>] [-AddSupportContact <String[]>] [-AddUserCategory <IResultObject[]>] [-AppCategory <String[]>] [-ApplyToLanguageById <Int32>] [-AutoInstall <Boolean>] [-CleanAppCategory] [-CleanUserCategory] [-ClearAppCatalog] [-ClearOwner] [-ClearSupportContact] [-DefaultLanguageId <Int32>] [-Description <String>] [-DisableWildcardHandling] [-DisplaySupersedenceInApplicationCatalog <Boolean>] [-DistributionPointSetting {AutoDownload | DeltaCopy | NoDownload}] [-DistributionPriority {High | Medium | Low}] [-ForceWildcardHandling] [-IconLocationFile <String>] [-IsFeatured <Boolean>] [-Keyword <String[]>] [-LinkText <String>] [-LocalizedApplicationName <String>] [-LocalizedDescription <String>] [-NewName <String>] [-OptionalReference <String>] [-Owner <String>] [-PassThru] [-PrivacyUrl <String>] [-Publisher <String>] [-ReleaseDate <DateTime>] [-RemoveAppCatalog <Int32[]>] [-RemoveAppCategoryName <String[]>] [-RemoveOwner <String[]>] [-RemoveSupportContact <String[]>] [-RemoveUserCategoryName <String[]>] [-SendToProtectedDistributionPoint <Boolean>] [-SoftwareVersion <String>] [-SupportContact <String>] [-UserCategory <String[]>] [-UserDocumentation <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
