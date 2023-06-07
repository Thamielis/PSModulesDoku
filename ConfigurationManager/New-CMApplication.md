New-CMApplication
-----------------




### Synopsis
Create an application.



---


### Description

Use this cmdlet to create an application. A Configuration Manager application defines the metadata about application. For more information, see Create applications in Configuration Manager (/mem/configmgr/apps/deploy-use/create-applications).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Convert-CMApplication](Convert-CMApplication)



* [ConvertFrom-CMApplication](ConvertFrom-CMApplication)



* [ConvertTo-CMApplication](ConvertTo-CMApplication)



* [Export-CMApplication](Export-CMApplication)



* [Get-CMApplication](Get-CMApplication)



* [Import-CMApplication](Import-CMApplication)



* [Remove-CMApplication](Remove-CMApplication)



* [Resume-CMApplication](Resume-CMApplication)



* [Set-CMApplication](Set-CMApplication)



* [Suspend-CMApplication](Suspend-CMApplication)



* [New-CMApplicationDisplayInfo](New-CMApplicationDisplayInfo)



* [Create applications in Configuration Manager](Create applications in Configuration Manager)





---


### Examples
#### Example 1: Create an application
```PowerShell
New-CMApplication -Name "Application01" -Description "New Application" -Publisher "Contoso" -SoftwareVersion "1.0.0.1" -OptionalReference "Reference" -ReleaseDate 2/24/2016 -AutoInstall $True -Owner "Administrator" -SupportContact "Administrator" -LocalizedName "Application01" -UserDocumentation "https://contoso.com/content" -LinkText "For more information" -LocalizedDescription "New Localized Application" -Keyword "application" -PrivacyUrl "https://contoso.com/library/privacy" -IsFeatured $True -IconLocationFile "\\central\icons\icon.png"
```



---


### Parameters
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



#### **AppCatalog**

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



#### **AutoInstall**

Set this parameter to $true to allow the app to be installed from the Install Application task sequence step without being deployed.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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

Don't use this parameter. The application catalog is no longer supported.






|Type       |Required|Position|PipelineInput|Aliases                                 |
|-----------|--------|--------|-------------|----------------------------------------|
|`[Boolean]`|false   |named   |False        |DisplaySupersedencesInApplicationCatalog|



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



#### **IsFeatured**

Set this parameter to $true to display this application as a featured app and highlight it in the Company Portal.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Keyword**

Specify a list of keywords in the selected language. These keywords help Software Center users search for the app.


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

Specify a description for this app in the selected language. The maximum length is 2048 characters.






|Type      |Required|Position|PipelineInput|Aliases                        |
|----------|--------|--------|-------------|-------------------------------|
|`[String]`|false   |named   |False        |LocalizedApplicationDescription|



#### **LocalizedName**

Specify the app name in the selected language. This name appears in Software Center.


A name is required for each language that you add.


The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|false   |named   |False        |LocalizedApplicationName|



#### **Name**

Specify a name for the app. The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



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
None





---


### Outputs
* IResultObject#SMS_ApplicationLatest


* IResultObject#SMS_Application






---


### Notes
For more information on this return object and its properties, see SMS_Application server WMI class (/mem/configmgr/develop/reference/apps/sms_application-server-wmi-class).



---


### Syntax
```PowerShell
New-CMApplication [-Name] <String> [-AddOwner <String[]>] [-AddSupportContact <String[]>] [-AppCatalog <AppDisplayInfo[]>] [-AutoInstall <Boolean>] [-DefaultLanguageId <Int32>] [-Description <String>] [-DisableWildcardHandling] [-DisplaySupersedenceInApplicationCatalog <Boolean>] [-ForceWildcardHandling] [-IconLocationFile <String>] [-IsFeatured <Boolean>] [-Keyword <String[]>] [-LinkText <String>] [-LocalizedDescription <String>] [-LocalizedName <String>] [-OptionalReference <String>] [-Owner <String>] [-PrivacyUrl <String>] [-Publisher <String>] [-ReleaseDate <DateTime>] [-SoftwareVersion <String>] [-SupportContact <String>] [-UserDocumentation <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
