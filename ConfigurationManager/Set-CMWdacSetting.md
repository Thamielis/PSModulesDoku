Set-CMWdacSetting
-----------------




### Synopsis
Modify an existing Microsoft Defender Application Control policy.



---


### Description

Modify an existing Microsoft Defender Application Control policy. Use New-CMWdacSetting (New-CMWdacSetting.md) to create a new management policy, and [Get-CMWdacSetting](Get-CMWdacSetting.md)to get an existing management policy.



---


### Related Links
* [Copy-CMWdacSetting](Copy-CMWdacSetting)



* [Get-CMWdacSetting](Get-CMWdacSetting)



* [New-CMWdacSetting](New-CMWdacSetting)



* [Remove-CMWdacSetting](Remove-CMWdacSetting)



* [Windows Defender Application Control management with Configuration Manager](Windows Defender Application Control management with Configuration Manager)





---


### Examples
#### Example 1: Add trusted binaries to an existing setting
```PowerShell
Get-CMWdacSetting -Name "My App Control setting" | Set-CMWdacSetting -TrustedFiles "xyz.exe", "abc.dll"
```



---


### Parameters
#### **Description**

Specify a new description for the policy object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableIntelligentSecurityGraph**

Use this parameter to authorize software that the Microsoft Intelligent Security Graph trusts. This service includes Windows Defender SmartScreen and other Microsoft services. For this software to be trusted, the device must be running Windows Defender SmartScreen and Windows 10 version 1709 or later.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnforcementMode**

Choose one of the following enforcement methods for Microsoft Defender Application Control:


* `EnforceMode`: Only trusted executables can run.


* `AuditMode`: Allow all executables to run. Add an entry to the Windows event log when untrusted executables run.



Valid Values:

* AuditMode
* EnforceMode






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[CMWDACEnforcementMode]`|false   |named   |False        |



#### **EnforceRestart**

After the client processes the policy, a restart is scheduled on the client. It follows the client settings for Computer Restart . Applications currently running on the device won't have the new Application Control policy applied to them until after the device restarts.


Set this parameter to `$true` to force the device to restart after the client applies the policy.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Use this parameter to change the name of the specified policy object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **TrustedFiles**

Add trust for specific files.






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[FileInfo[]]`|false   |named   |False        |



#### **TrustedFolders**

Add trust for specific folders.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[DirectoryInfo[]]`|false   |named   |False        |



#### **WdacSettings**

Specify a policy object to modify. Use the Get-CMWdacSettings cmdlet to get this object.






|Type              |Required|Position|PipelineInput |
|------------------|--------|--------|--------------|
|`[CMWdacSettings]`|true    |1       |True (ByValue)|





---


### Inputs
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.WDAC.CMWdacSettings





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.WDAC.CMWdacSettings






---


### Notes




---


### Syntax
```PowerShell
Set-CMWdacSetting [-WdacSettings] <CMWdacSettings> [-Description <String>] [-DisableWildcardHandling] [-EnableIntelligentSecurityGraph <Boolean>] [-EnforcementMode {AuditMode | EnforceMode}] [-EnforceRestart <Boolean>] [-ForceWildcardHandling] [-Name <String>] [-PassThru] [-TrustedFiles <FileInfo[]>] [-TrustedFolders <DirectoryInfo[]>] [<CommonParameters>]
```
