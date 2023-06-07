Get-CMWinPEOptionalComponentInfo
--------------------------------




### Synopsis
Get a Windows PE optional component.



---


### Description

Use this cmdlet to get a Windows PE (WinPE) optional component. Use this object to add it to or remove it from a boot image with the Set-CMBootImage (Set-CMBootImage.md) cmdlet. For more information, see [Manage boot images - Optional components](/mem/configmgr/osd/get-started/manage-boot-images#optional-components).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMBootImage](Set-CMBootImage)



* [Manage boot images - Optional components](Manage boot images - Optional components)





---


### Examples
#### Example 1: Get optional components and add to a boot image
```PowerShell
$netfxOC = Get-CMWinPEOptionalComponentInfo -Architecture 'x64' -Name 'WinPE-NetFX' -LanguageId 1033
$pwshOC = Get-CMWinPEOptionalComponentInfo -Architecture 'x64' -Name 'WinPE-PowerShell' -LanguageId 1033
$OCs = @($netfxOC, $pwshOC)

Set-CMBootImage -Id 'XYZ00556' -AddOptionalComponent $OCs
```



---


### Parameters
#### **Architecture**

Specify the architecture of a WinPE optional component.



Valid Values:

* X64
* X86






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **LanguageId**

Specify the language ID for the optional component.


This ID is the decimal equivalent of the Windows language ID . For example, `1033` is `0x0409` for English (United States) , and `2070` is `0x0816` for Portuguese (Portugal) . For more information, see [MS-LCID]: Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).


Configuration Manager supports 22 languages. For more information, see Client languages (/mem/configmgr/core/servers/deploy/install/language-packs#client-languages).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|false   |named   |False        |



#### **Name**

Specify the name of the WinPE optional component to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UniqueId**

Specify the unique ID of the WinPE optional component to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_WinPEOptionalComponentInfo


* IResultObject#SMS_WinPEOptionalComponentInfo






---


### Notes
For more information on this return object and its properties, see SMS_WinPEOptionalComponentInfo server WMI class (/mem/configmgr/develop/reference/osd/sms_winpeoptionalcomponentinfo-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMWinPEOptionalComponentInfo -Architecture {X64 | X86} [-DisableWildcardHandling] [-ForceWildcardHandling] [-LanguageId <UInt32>] [-Name <String>] [<CommonParameters>]
```
```PowerShell
Get-CMWinPEOptionalComponentInfo [-DisableWildcardHandling] [-ForceWildcardHandling] -UniqueId <String> [<CommonParameters>]
```
