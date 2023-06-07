New-CMBMSUserExemptionPolicy
----------------------------




### Synopsis
Create a policy to configure instructions for users to request exemption from BitLocker protection.



---


### Description

Use this cmdlet to create a policy to configure instructions for users to request exemption from BitLocker protection. These instructions include a URL, email address, or phone number.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: Create a policy with URL as contact method
```PowerShell
New-CMBMSUserExemptionPolicy -PolicyState Enabled -MaxDays 6 -ContactMethod Url -ContactDetail "https://contoso.com/bitlockerexemption"
```

#### Example 2: Create a policy with email as contact method
```PowerShell
New-CMBMSUserExemptionPolicy -PolicyState Enabled -MaxDays 4 -ContactMethod Email -ContactDetail "bitlockerexemption@contoso.com"
```

#### Example 3: Create a policy with phone as contact method
```PowerShell
New-CMBMSUserExemptionPolicy -PolicyState Enabled -MaxDays 16 -ContactMethod Phone -ContactDetail "515-555-8127"
```



---


### Parameters
#### **ContactDetail**

Based on the -ContactMethod parameter, use this parameter to specify the specific string to include. For example, if -ContactMethod is `Phone`, specify a value phone number as the value of this parameter. The URL and email address display as links.


* The URL format is `"https://YourExemptionWebSite"`


* The email address format is `"alias@domain.tld"`


BitLocker automatically creates a link with the following format: `mailto: xyz@abc.com?subject=Request exemption from BitLocker protection"`


* The phone number format is as necessary for your local standard. For example, in the United States: `"123-456-7890"`


BitLocker displays the following message: Please call 123-456-7890 for applying exemption






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ContactMethod**

Select how users submit an exemption request. Use the -ContactDetail parameter to specify the custom string for this method.



Valid Values:

* Url
* Email
* Phone






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[ContactMethod]`|false   |named   |False        |



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



#### **MaxDays**

Use this parameter to specify how many days the user can postpone an enforced policy. By default, this value is `7` days (one week).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|false   |named   |False        |



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, and provide a URL, email address, or phone number, the user can apply for exemption. BitLocker displays instructions on how to apply for  exemption from BitLocker protection. Use the -ContactMethod and ContactDetail parameters to configure the specific method.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy, Windows doesn't display the exemption request instructions to users.



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
New-CMBMSUserExemptionPolicy [-ContactDetail <String>] [-ContactMethod {Url | Email | Phone}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaxDays <UInt32>] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
