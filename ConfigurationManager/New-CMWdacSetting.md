New-CMWdacSetting
-----------------




### Synopsis
Create a Microsoft Defender Application Control settings policy object.



---


### Description

Create a Microsoft Defender Application Control settings policy object.



Use the New-CMSettingDeployment (New-CMSettingDeployment.md)cmdlet to deploy this setting to a collection.



---


### Related Links
* [Copy-CMWdacSetting](Copy-CMWdacSetting)



* [Get-CMWdacSetting](Get-CMWdacSetting)



* [Remove-CMWdacSetting](Remove-CMWdacSetting)



* [Set-CMWdacSetting](Set-CMWdacSetting)



* [New-CMSettingDeployment](New-CMSettingDeployment)



* [Windows Defender Application Control management with Configuration Manager](Windows Defender Application Control management with Configuration Manager)





---


### Examples
#### Example 1: New audit mode Application Control policy
```PowerShell
New-CMWdacSetting -Name "NewAudit" -EnforcementMode AuditMode
```

#### Example 2: New policy that doesn't reboot the client
```PowerShell
New-CMWdacSetting -Name "NewNoReboot" -EnforceRestart $false
```

#### Example 3: New policy custom trusted binaries
```PowerShell
New-CMWdacSetting -Name "NewTrustedFiles" -TrustedFiles "abc.exe", "xyz.dll"
```



---


### Parameters
#### **Description**

Specify an optional description to better identify this policy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableIntelligentSecurityGraph**

Add this parameter to authorize software that the Microsoft Intelligent Security Graph trusts. This service includes Windows Defender SmartScreen and other Microsoft services. For this software to be trusted, the device must be running Windows Defender SmartScreen and Windows 10 version 1709 or later.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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

Specify a name for this policy to identify it.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.WDAC.CMWdacSettings






---


### Notes




---


### Syntax
```PowerShell
New-CMWdacSetting [-Description <String>] [-DisableWildcardHandling] [-EnableIntelligentSecurityGraph] [-EnforcementMode {AuditMode | EnforceMode}] [-EnforceRestart <Boolean>] [-ForceWildcardHandling] -Name <String> [-TrustedFiles <FileInfo[]>] [-TrustedFolders <DirectoryInfo[]>] [<CommonParameters>]
```
