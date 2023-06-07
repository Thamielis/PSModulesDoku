New-CMApplicationGroup
----------------------




### Synopsis
Create a new application group.



---


### Description

Use this cmdlet to create an application group. Use an application group to deploy multiple applications to a collection as a single deployment. The metadata you specify about the app group is seen in Software Center as a single entity. You can order the apps in the group so that the client installs them in a specific order. For more information, see Create application groups (/mem/configmgr/apps/deploy-use/create-app-groups).



There are some settings of an app group that you can't configure when you create it. To configure other settings, use the Set-CMApplicationGroup (Set-CMApplicationGroup.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplicationGroup](Get-CMApplicationGroup)



* [Remove-CMApplicationGroup](Remove-CMApplicationGroup)



* [Set-CMApplicationGroup](Set-CMApplicationGroup)



* [New-CMApplicationDisplayInfo](New-CMApplicationDisplayInfo)



* [Get-CMApplicationGroupDeployment](Get-CMApplicationGroupDeployment)



* [New-CMApplicationGroupDeployment](New-CMApplicationGroupDeployment)



* [Remove-CMApplicationGroupDeployment](Remove-CMApplicationGroupDeployment)



* [Set-CMApplicationGroupDeployment](Set-CMApplicationGroupDeployment)



* [Create application groups](Create application groups)





---


### Examples
#### Example 1: Create a group with two apps
```PowerShell
$apps = @('LOB Framework','CA UI')

New-CMApplicationGroup -Name 'Central app' -AddApplication $apps -Description 'Central app group' -Publisher 'Contoso IT' -SoftwareVersion '1.1.2' -ReleaseDate (Get-Date) -AddOwner 'jqpublic' -AddSupportContact 'jdoe' -LocalizedAppGroupName 'Central app'
```



---


### Parameters
#### **AddApplication**

Specify a string array of app names to add to the group. If you already have an app object from another cmdlet like Get-CMApplication (Get-CMApplication.md), this value is the **LocalizedDisplayName** property. For example: `$appList = @($app1.LocalizedDisplayName,$app2.LocalizedDisplayName)`






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|true    |named   |False        |AddApplications|



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



#### **AppGroupCatalog**

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



#### **Name**

Specify a name for the app group. The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|Aliases                                      |
|----------|--------|--------|-------------|---------------------------------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName<br/>ApplicationGroupName|



#### **OptionalReference**

Specify an optional string to help you find the app group in the console. The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
None





---


### Outputs
* IResultObject#SMS_ApplicationGroup






---


### Notes
This cmdlet returns the SMS_ApplicationGroup WMI class object.



---


### Syntax
```PowerShell
New-CMApplicationGroup [-Name] <String> -AddApplication <String[]> [-AddOwner <String[]>] [-AddSupportContact <String[]>] [-AppGroupCatalog <AppDisplayInfo[]>] [-DefaultLanguageId <Int32>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IconLocationFile <String>] [-Keyword <String[]>] [-LinkText <String>] [-LocalizedDescription <String>] [-LocalizedName <String>] [-OptionalReference <String>] [-PrivacyUrl <String>] [-Publisher <String>] [-ReleaseDate <DateTime>] [-SoftwareVersion <String>] [-UserDocumentation <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
