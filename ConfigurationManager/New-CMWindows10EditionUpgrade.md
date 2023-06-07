New-CMWindows10EditionUpgrade
-----------------------------




### Synopsis
Create a Windows 10 edition upgrade policy.



---


### Description

Create a Windows 10 edition upgrade policy. Specify a product key or license information to upgrade Windows 10 to a different edition. For more information, see Upgrade Windows devices to a new edition with Configuration Manager (/mem/configmgr/compliance/deploy-use/upgrade-windows-version).



---


### Related Links
* [Get-CMWindowsEditionUpgradeConfigurationItem](Get-CMWindowsEditionUpgradeConfigurationItem)



* [Remove-CMWindows10EditionUpgrade](Remove-CMWindows10EditionUpgrade)



* [Set-CMWindows10EditionUpgrade](Set-CMWindows10EditionUpgrade)



* [Upgrade Windows devices to a new edition with Configuration Manager](Upgrade Windows devices to a new edition with Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
New-CMWindows10EditionUpgrade -Name "NewEditionPolicyByKey" -WindowsEdition Windows10Enterprise -ProductKey "123ab-cd456-789ef-2j3k4-0ghi1"
```



---


### Parameters
#### **Description**

Specify an optional description for the policy.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EditionUpgradeWithClient**

Use this parameter to specify the type of edition upgrade to create:


* `$true`: The policy is for devices managed with the Configuration Manager client. Use the ProductKey parameter to specify the license key. - `$false`: This policy is for devices running Windows 10 Mobile that you manage with on-premises MDM. Use the LicenseFile parameter to provide the XML license file.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **LicenseFile**

When you set the EditionUpgradeWithClient parameter to `$false`, use this parameter to specify the path to the XML license file. Get the license file from the Microsoft Volume Licensing Service Center (VLSC). This file contains the licensing information for the new version of Windows on all devices you target with the policy. Download the ISO file for Windows 10 Mobile Enterprise , which includes the licensing XML.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specify a name for this Windows 10 edition upgrade policy.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **ProductKey**

When you set the EditionUpgradeWithClient parameter to `$true`, use this parameter to specify a valid product key for the new version of Windows. This product key can be a multiple activation key (MAK), or a generic volume licensing key (GVLK). A GVLK is also referred to as a key management service (KMS) client setup key. For more information, see Plan for volume activation (/windows/deployment/volume-activation/plan-for-volume-activation-client). For a list of KMS client setup keys, see [Appendix A](/windows-server/get-started/kmsclientkeys)of the Windows Server activation guide.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **WindowsEdition**

Specify the target edition of Windows 10 that corresponds with the LicenseFile or ProductKey .



Valid Values:

* None
* Windows10Enterprise
* Windows10EnterpriseN
* Windows10Education
* Windows10EducationN
* WindowsPhone10
* HolographicEnterprise






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[WindowsEditionType]`|false   |named   |False        |



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
* IResultObject#SMS_ConfigurationPolicy






---


### Notes




---


### Syntax
```PowerShell
New-CMWindows10EditionUpgrade [-Description <String>] [-DisableWildcardHandling] [-EditionUpgradeWithClient <Boolean>] [-ForceWildcardHandling] [-LicenseFile <String>] -Name <String> [-ProductKey <String>] [-WindowsEdition {Windows10Enterprise | Windows10Education | Windows10EnterpriseN | Windows10EducationN | WindowsPhone10 | HolographicEnterprise}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
