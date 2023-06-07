New-CMMoreInfoUrlPolicy
-----------------------




### Synopsis
Create a policy to specify the Security Policy link that BitLocker displays to users.



---


### Description

Create a policy to specify the Security Policy link that BitLocker displays to users. The link should point to your organization's internal security policy. This policy site should provide users with information about your disk encryption requirements. BitLocker displays this link when it prompts users to encrypt a drive.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New enabled policy with specified URL
```PowerShell
New-CMMoreInfoUrlPolicy -PolicyState Enabled -MoreInfoUrl https://contoso.com/bdepolicy
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



#### **MoreInfoUrl**

Specify a URL for your organization's internal security policy about your disk encryption requirements. BitLocker displays this link when it prompts users to encrypt a drive.






|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[Uri]`|false   |named   |False        |



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, configure the URL for the Security Policy link.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy, BitLocker doesn't display this link for users.



Valid Values:

* Enabled
* Disabled
* NotConfigured






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[State]`|false   |named   |False        |





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
New-CMMoreInfoUrlPolicy [-DisableWildcardHandling] [-ForceWildcardHandling] [-MoreInfoUrl <Uri>] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
