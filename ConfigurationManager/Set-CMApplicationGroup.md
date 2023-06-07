Set-CMApplicationGroup
----------------------




### Synopsis
Configure an existing application group.



---


### Description

Use this cmdlet to configure the settings of an existing application group. Use an app group to deploy multiple applications to a collection as a single deployment. The metadata you specify about the app group is seen in Software Center as a single entity. You can order the apps in the group so that the client installs them in a specific order. For more information, see Create application groups (/mem/configmgr/apps/deploy-use/create-app-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplicationGroup](Get-CMApplicationGroup)



* [New-CMApplicationGroup](New-CMApplicationGroup)



* [Remove-CMApplicationGroup](Remove-CMApplicationGroup)



* [New-CMApplicationDisplayInfo](New-CMApplicationDisplayInfo)



* [Get-CMApplicationGroupDeployment](Get-CMApplicationGroupDeployment)



* [New-CMApplicationGroupDeployment](New-CMApplicationGroupDeployment)



* [Remove-CMApplicationGroupDeployment](Remove-CMApplicationGroupDeployment)



* [Set-CMApplicationGroupDeployment](Set-CMApplicationGroupDeployment)



* [Create application groups](Create application groups)





---


### Examples
#### Example 1: Rename an app group
```PowerShell
$appgroup = Get-CMApplicationGroup -Name "Central app"
Set-CMApplicationGroup -InputObject $appgroup -NewName "Contoso Central App"
```

#### Example 2: Add a localized name
```PowerShell
Set-CMApplicationGroup -Name "Contoso Welcome app" -ApplyToLanguageById 60 -LocalizedName "Fáilte romhat"
```



---


### Parameters
#### **AddAppCatalog**

Use this parameter to specify a Software Center entry for a specific language. This entry can include all of the localized information about the app group:


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

Specify one or more administrative category objects to help you filter and find the app group in the console. To get these objects, use the Get-CMCategory (Get-CMCategory.md)cmdlet. These categories are of type AppCategories .


To add categories to help users filter and find applications in Software Center, use the AddUserCategory parameter.






|Type               |Required|Position|PipelineInput|Aliases         |
|-------------------|--------|--------|-------------|----------------|
|`[IResultObject[]]`|false   |named   |False        |AddAppCategories|



#### **AddApplication**

Specify a string array of app names to add to the group. If you already have an app object from another cmdlet like Get-CMApplication (Get-CMApplication.md), this value is the **LocalizedDisplayName** property. For example: `$appList = @($app1.LocalizedDisplayName,$app2.LocalizedDisplayName)`






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|false   |named   |False        |AddApplications|



#### **AddOwner**

Specify one or more administrative users who are responsible for this app group.






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



#### **ApplyToLanguageById**

For settings that display in Software Center, use this parameter to specify the language ID for the settings.


This ID is the decimal equivalent of the Windows language ID. For example, `1033` is `0x0409` for English (United States) , and `2108` is `0x083C` for Irish (Ireland) . For more information, see [MS-LCID]: Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).


For example, to add a localized app name for Irish (Ireland) :


`-ApplyToLanguageById 2108 -LocalizedName "Fáilte romhat"`






|Type     |Required|Position|PipelineInput|Aliases                       |
|---------|--------|--------|-------------|------------------------------|
|`[Int32]`|false   |named   |False        |ApplySettingToSpecificLanguage|



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

Specify an optional administrator comment for the app group. The maximum length is 2048 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **IconLocationFile**

Specify the path to the file that contains the icon for this app group. Icons can have pixel dimensions of up to 512x512. The file can be of the following image and icon file types:


* DLL


* EXE


* JPG


* ICO


* PNG






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Id**

Specify the ID of the app group to configure. This value is the same as the CI_ID , for example `1025866`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify an app group object to configure. To get this object, use the Get-CMApplicationGroup (Get-CMApplicationGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |0       |True (ByValue)|ApplicationGroup|



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



#### **LocalizedDescription**

Specify a description for this app group in the selected language. The maximum length is 2048 characters.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|false   |named   |False        |LocalizedAppGroupDescription|



#### **LocalizedName**

Specify the app group name in the selected language. This name appears in Software Center.


A name is required for each language that you add.


The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|false   |named   |False        |LocalizedAppGroupName|



#### **ModelName**

Specify the application model identifier of the app group to configure. This value is also known as the CI Unique ID . For example, `ScopeId_0D7D8B60-F2F9-484A-B9F3-4A8B68D14D59/ApplicationGroup_047fbf05-55f4-42ab-9581-e63fd0337fed`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Name**

Specify the name of the app group to configure.






|Type      |Required|Position|PipelineInput|Aliases                                      |
|----------|--------|--------|-------------|---------------------------------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName<br/>ApplicationGroupName|



#### **NewName**

Use this parameter to rename the app group. The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OptionalReference**

Specify an optional string to help you find the app group in the console. The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PrivacyUrl**

Specify a website address to the privacy statement for the app group. The format needs to be a valid URL, for example `https://contoso.com/privacy`. The maximum length of the entire string is 128 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Publisher**

Specify optional vendor information for this app group. The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |Manufacturer|



#### **ReleaseDate**

Specify a date object for when this app group was released. To get this object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)built-in cmdlet.






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



#### **RemoveApplication**

Specify an array of application names to remove from this group.






|Type        |Required|Position|PipelineInput|Aliases           |
|------------|--------|--------|-------------|------------------|
|`[String[]]`|false   |named   |False        |RemoveApplications|



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



#### **SoftwareVersion**

Specify an optional version string for the app group. The maximum length is 64 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserDocumentation**

Specify the location of a file from which Software Center users can get more information about this app group. This location is a website address, or a network path and file name. Make sure that users have access to this location.


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
* IResultObject#SMS_ApplicationGroup






---


### Notes




---


### Syntax
```PowerShell
Set-CMApplicationGroup [-Id] <Int32> [-AddAppCatalog <AppDisplayInfo[]>] [-AddAppCategory <IResultObject[]>] [-AddApplication <String[]>] [-AddOwner <String[]>] [-AddSupportContact <String[]>] [-AddUserCategory <IResultObject[]>] [-ApplyToLanguageById <Int32>] [-CleanAppCategory] [-CleanUserCategory] [-ClearAppCatalog] [-ClearOwner] [-ClearSupportContact] [-DefaultLanguageId <Int32>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IconLocationFile <String>] [-Keyword <String[]>] [-LinkText <String>] [-LocalizedDescription <String>] [-LocalizedName <String>] [-NewName <String>] [-OptionalReference <String>] [-PassThru] [-PrivacyUrl <String>] [-Publisher <String>] [-ReleaseDate <DateTime>] [-RemoveAppCatalog <Int32[]>] [-RemoveAppCategoryName <String[]>] [-RemoveApplication <String[]>] [-RemoveOwner <String[]>] [-RemoveSupportContact <String[]>] [-RemoveUserCategoryName <String[]>] [-SoftwareVersion <String>] [-UserDocumentation <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationGroup [-InputObject] <IResultObject> [-AddAppCatalog <AppDisplayInfo[]>] [-AddAppCategory <IResultObject[]>] [-AddApplication <String[]>] [-AddOwner <String[]>] [-AddSupportContact <String[]>] [-AddUserCategory <IResultObject[]>] [-ApplyToLanguageById <Int32>] [-CleanAppCategory] [-CleanUserCategory] [-ClearAppCatalog] [-ClearOwner] [-ClearSupportContact] [-DefaultLanguageId <Int32>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IconLocationFile <String>] [-Keyword <String[]>] [-LinkText <String>] [-LocalizedDescription <String>] [-LocalizedName <String>] [-NewName <String>] [-OptionalReference <String>] [-PassThru] [-PrivacyUrl <String>] [-Publisher <String>] [-ReleaseDate <DateTime>] [-RemoveAppCatalog <Int32[]>] [-RemoveAppCategoryName <String[]>] [-RemoveApplication <String[]>] [-RemoveOwner <String[]>] [-RemoveSupportContact <String[]>] [-RemoveUserCategoryName <String[]>] [-SoftwareVersion <String>] [-UserDocumentation <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationGroup [-AddAppCatalog <AppDisplayInfo[]>] [-AddAppCategory <IResultObject[]>] [-AddApplication <String[]>] [-AddOwner <String[]>] [-AddSupportContact <String[]>] [-AddUserCategory <IResultObject[]>] [-ApplyToLanguageById <Int32>] [-CleanAppCategory] [-CleanUserCategory] [-ClearAppCatalog] [-ClearOwner] [-ClearSupportContact] [-DefaultLanguageId <Int32>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IconLocationFile <String>] [-Keyword <String[]>] [-LinkText <String>] [-LocalizedDescription <String>] [-LocalizedName <String>] -ModelName <String> [-NewName <String>] [-OptionalReference <String>] [-PassThru] [-PrivacyUrl <String>] [-Publisher <String>] [-ReleaseDate <DateTime>] [-RemoveAppCatalog <Int32[]>] [-RemoveAppCategoryName <String[]>] [-RemoveApplication <String[]>] [-RemoveOwner <String[]>] [-RemoveSupportContact <String[]>] [-RemoveUserCategoryName <String[]>] [-SoftwareVersion <String>] [-UserDocumentation <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationGroup [-Name] <String> [-AddAppCatalog <AppDisplayInfo[]>] [-AddAppCategory <IResultObject[]>] [-AddApplication <String[]>] [-AddOwner <String[]>] [-AddSupportContact <String[]>] [-AddUserCategory <IResultObject[]>] [-ApplyToLanguageById <Int32>] [-CleanAppCategory] [-CleanUserCategory] [-ClearAppCatalog] [-ClearOwner] [-ClearSupportContact] [-DefaultLanguageId <Int32>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IconLocationFile <String>] [-Keyword <String[]>] [-LinkText <String>] [-LocalizedDescription <String>] [-LocalizedName <String>] [-NewName <String>] [-OptionalReference <String>] [-PassThru] [-PrivacyUrl <String>] [-Publisher <String>] [-ReleaseDate <DateTime>] [-RemoveAppCatalog <Int32[]>] [-RemoveAppCategoryName <String[]>] [-RemoveApplication <String[]>] [-RemoveOwner <String[]>] [-RemoveSupportContact <String[]>] [-RemoveUserCategoryName <String[]>] [-SoftwareVersion <String>] [-UserDocumentation <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
