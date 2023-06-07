New-CMBlmSetting
----------------




### Synopsis
Create a BitLocker management settings policy.



---


### Description

Create a BitLocker management settings policy. You configure the specific policies with other cmdlets, and then use this cmdlet to create the management policy. For more information on the specific policy cmdlets, see Related links (#related-links).



Use the New-CMSettingDeployment (New-CMSettingDeployment.md)cmdlet to deploy this setting to a collection.



---


### Related Links
* [New-CMBLEncryptionMethodPolicy](New-CMBLEncryptionMethodPolicy)



* [New-CMBLEncryptionMethodWithXts](New-CMBLEncryptionMethodWithXts)



* [New-CMBMSClientConfigureCheckIntervalPolicy](New-CMBMSClientConfigureCheckIntervalPolicy)



* [New-CMBMSFDVEncryptionPolicy](New-CMBMSFDVEncryptionPolicy)



* [New-CMBMSOSDEncryptionPolicy](New-CMBMSOSDEncryptionPolicy)



* [New-CMBMSUserExemptionPolicy](New-CMBMSUserExemptionPolicy)



* [New-CMEnhancedPIN](New-CMEnhancedPIN)



* [New-CMFDVDenyWriteAccessPolicy](New-CMFDVDenyWriteAccessPolicy)



* [New-CMFDVPassPhrasePolicy](New-CMFDVPassPhrasePolicy)



* [New-CMMoreInfoUrlPolicy](New-CMMoreInfoUrlPolicy)



* [New-CMNoOverwritePolicy](New-CMNoOverwritePolicy)



* [New-CMOSPassphrase](New-CMOSPassphrase)



* [New-CMPrebootRecoveryInfo](New-CMPrebootRecoveryInfo)



* [New-CMRDVConfigureBDEPolicy](New-CMRDVConfigureBDEPolicy)



* [New-CMRDVDenyWriteAccessPolicy](New-CMRDVDenyWriteAccessPolicy)



* [New-CMRDVPassPhrasePolicy](New-CMRDVPassPhrasePolicy)



* [New-CMScCompliancePolicy](New-CMScCompliancePolicy)



* [New-CMTpmAutoResealPolicy](New-CMTpmAutoResealPolicy)



* [New-CMUidPolicy](New-CMUidPolicy)



* [New-CMUseFddEnforcePolicy](New-CMUseFddEnforcePolicy)



* [New-CMUseOsEnforcePolicy](New-CMUseOsEnforcePolicy)



* [Set-CMBlmPlaintextStorage](Set-CMBlmPlaintextStorage)



* [New-CMSettingDeployment](New-CMSettingDeployment)



* [Copy-CMBlmSetting](Copy-CMBlmSetting)



* [Get-CMBlmSetting](Get-CMBlmSetting)



* [Remove-CMBlmSetting](Remove-CMBlmSetting)



* [Set-CMBlmSetting](Set-CMBlmSetting)



* [New-CMSettingDeployment](New-CMSettingDeployment)



* [Deploy BitLocker management](Deploy BitLocker management)





---


### Examples
#### Example 1: Create a BitLocker setting with some standard policies
```PowerShell
$policies = @()

$policies += New-CMBLEncryptionMethodWithXts  -PolicyState Enabled -OSDriveEncryptionMethod AesXts256
$policies += New-CMBMSOSDEncryptionPolicy -PolicyState Enabled -Protector TpmOnly
$Policies += New-CMUseOsEnforcePolicy -PolicyState Enabled -GracePeriodDays 0
$Policies += New-CMBMSClientConfigureCheckIntervalPolicy -PolicyState Enabled -ClientWakeupFrequencyMinutes 9

New-CMBlmSetting -Name "BLM Settings" -Policies $policies
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



#### **Policies**

Specify an array of BitLocker policies to include. For more information on the specific policy cmdlets, see Related links (#related-links).


If you don't specify any policies with the -Policies parameter, the default policy is a single, not configured, OS drive encryption policy. For more information on this default policy type, see New-CMBMSOSDEncryptionPolicy (New-CMBMSOSDEncryptionPolicy.md).






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[PolicyObject[]]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.BitLockerManagement.BlmSettings






---


### Notes




---


### Syntax
```PowerShell
New-CMBlmSetting [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Policies <PolicyObject[]>] [<CommonParameters>]
```
