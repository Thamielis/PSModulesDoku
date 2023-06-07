New-CMApplicationDisplayInfo
----------------------------




### Synopsis
Create a Software Center entry for an application or application group.



---


### Description

Use this cmdlet to create a Software Center entry for an application or application group. Specify information about how you want to display this app or app group to users when they browse the Software Center. To provide information in a specific language, specify the language ID.



This cmdlet creates an object that you can pass to the New-CMApplication , New-CMApplicationGroup , Set-CMApplication , and Set-CMApplicationGroup cmdlets.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMApplication](New-CMApplication)



* [Set-CMApplication](Set-CMApplication)



* [New-CMApplicationGroup](New-CMApplicationGroup)



* [Set-CMApplicationGroup](Set-CMApplicationGroup)





---


### Examples
#### Example 1
```PowerShell
$welcomeAppInfoIrish = New-CMApplicationDisplayInfo -Description "Fáilte a Contoso! Go raibh maith agat faoi theacht chugainn." -IconLocationFile "\\central\icons\welcome.ico" -Keyword "fostaí","nua" -LanguageId 60 -LinkText "Mar eolas duit" -PrivacyUrl "https://contoso.com/privacy" -Title "Fáilte romhat" -UserDocumentation "https://my.contoso.com/welcome"

Set-CMApplicationGroup -Name "Contoso Welcome app" -AddAppCatalog $welcomeAppInfoIrish
```



---


### Parameters
#### **Description**

Specify a description for this app in the specified language. The maximum length is 2048 characters.






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



#### **IconLocationFile**

Specify the path to the file that contains the icon for the app. Icons can have pixel dimensions of up to 512x512. The file can be of the following image and icon file types:


* DLL


* EXE


* JPG


* ICO


* PNG






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Keyword**

Specify a list of keywords in the specified language. These keywords help Software Center users search for the app.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **LanguageId**

Use this parameter to specify the language ID for the settings.


This ID is the decimal equivalent of the Windows language ID. For example, `1033` is `0x0409` for English (United States) , and `2108` is `0x083C` for Irish (Ireland) . For more information, see [MS-LCID]: Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **LinkText**

When you use the UserDocumentation parameter, use this parameter to show a string in place of "Additional information" in Software Center. The maximum length is 128 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PrivacyUrl**

Specify a website address to the privacy statement for the app. The format needs to be a valid URL, for example `https://contoso.com/privacy`. The maximum length of the entire string is 128 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Title**

Specify the app name in the specified language. This name appears in Software Center. The maximum length is 256 characters.






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[String]`|true    |named   |False        |LocalizedName|



#### **UserDocumentation**

Specify the location of a file from which Software Center users can get more information about this app. This location is a website address, or a network path and file name. Make sure that users have access to this location.


The maximum length of the entire string is 256 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* AppDisplayInfo






---


### Notes




---


### Syntax
```PowerShell
New-CMApplicationDisplayInfo [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IconLocationFile <String>] [-Keyword <String[]>] -LanguageId <Int32> [-LinkText <String>] [-PrivacyUrl <String>] -Title <String> [-UserDocumentation <String>] [<CommonParameters>]
```
