New-CMPrebootRecoveryInfo
-------------------------




### Synopsis
Configure the recovery message that the pre-boot key recovery screen displays when the OS drive is locked.



---


### Description

Use this cmdlet to configure the entire recovery message or replace the existing URL the pre-boot key recovery screen shows when the OS drive is locked.



If you use both -UseRecoveryUrl and -UseRecoveryMessage parameters, the pre-boot key recovery screen displays the default BitLocker recovery message and URL. If you previously configured a custom recovery message or URL and want to revert to the default message, keep the policy enabled and use both -UseRecoveryUrl and -UseRecoveryMessage parameters



> [!NOTE] > Pre-boot doesn't support all characters and languages. Test the characters that you want to use for the custom message or URL. Make sure the pre-boot recovery screen correctly displays your custom message or URL.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New enabled policy with a custom recovery message and URL
```PowerShell
New-CMPrebootRecoveryInfo -PolicyState Enabled -UseRecoveryMessage -RecoveryMessage "Contact the Contoso Helpdesk at 515-555-8127 or https://contoso.com/bitlockerrecovery"
```

#### Example 2: New enabled policy with a custom recovery URL
```PowerShell
New-CMPrebootRecoveryInfo -PolicyState Enabled -UseRecoveryUrl -RecoveryUrl https://contoso.com/bitlockerrecovery
```



---


### Parameters
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



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, BitLocker uses the custom information that you specify.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy, BitLocker uses the default information.



Valid Values:

* Enabled
* Disabled
* NotConfigured






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[State]`|false   |named   |False        |



#### **RecoveryMessage**

Specify a custom message to display on the pre-boot recovery screen. If you also want to specify a recovery URL, include it as part of this custom recovery message. The maximum string length is 32,768 characters. Use this parameter with the -UseRecoveryMessage parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RecoveryUrl**

Replace the default URL displayed in the pre-boot BitLocker recovery screen. The maximum URI length is 32,768 characters. Use this parameter with the -UseRecoveryUrl parameter.






|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[Uri]`|false   |named   |False        |



#### **UseRecoveryMessage**

If you add this parameter, the pre-boot key recovery screen displays the value of -RecoveryMessage .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UseRecoveryUrl**

If you add this parameter, the URL you specify for -RecoveryUrl replaces the default URL in the default recovery message.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.AdminConsole.BitlockerManagement.PolicyObject






---


### Notes




---


### Syntax
```PowerShell
New-CMPrebootRecoveryInfo [-DisableWildcardHandling] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [-RecoveryMessage <String>] [-RecoveryUrl <Uri>] [-UseRecoveryMessage] [-UseRecoveryUrl] [<CommonParameters>]
```
