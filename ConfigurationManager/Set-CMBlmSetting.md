Set-CMBlmSetting
----------------




### Synopsis
Modify an existing BitLocker management policy setting.



---


### Description

Modify an existing BitLocker management policy setting. Use New-CMBlmSetting (New-CMBlmSetting.md) to create a new management policy, and [Get-CMBlmSetting](Get-CMBlmSetting.md)to get an existing management policy.



---


### Related Links
* [Copy-CMBlmSetting](Copy-CMBlmSetting)



* [Get-CMBlmSetting](Get-CMBlmSetting)



* [New-CMBlmSetting](New-CMBlmSetting)



* [Remove-CMBlmSetting](Remove-CMBlmSetting)



* [Deploy BitLocker management](Deploy BitLocker management)





---


### Examples
#### Example 1: Add a new policy to an existing setting
```PowerShell
Get-CMBlmSetting -Name "My BitLocker settings" | Set-CMBlmSetting -Policies (New-CMBMSOSDEncryptionPolicy -PolicyState Enabled -Protector TpmOnly)
```



---


### Parameters
#### **BlmSettings**

Specify a BitLocker management policy settings object to configure. Use the Get-CMBlmSetting (Get-CMBlmSetting.md)to get this object.






|Type           |Required|Position|PipelineInput |
|---------------|--------|--------|--------------|
|`[BlmSettings]`|true    |1       |True (ByValue)|



#### **Description**

Specify a new description for the BitLocker management policy object.






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

Use this parameter to change the name of the specified BitLocker management policy object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Policies**

Specify an array of BitLocker policies to include. For more information on the specific policy cmdlets, see the Related links in the New-CMBlmSetting (New-CMBlmSetting.md)cmdlet.


If you don't specify any policies with the -Policies parameter, the default policy is a single, not configured, OS drive encryption policy. For more information on this default policy type, see New-CMBMSOSDEncryptionPolicy (New-CMBMSOSDEncryptionPolicy.md).






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[PolicyObject[]]`|false   |named   |False        |



#### **Precedence**

Change the priority order of this policy. If you deploy multiple policies to the same client, the lowest number takes precedence.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.BitLockerManagement.BlmSettings





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.BitLockerManagement.BlmSettings






---


### Notes




---


### Syntax
```PowerShell
Set-CMBlmSetting [-BlmSettings] <BlmSettings> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-PassThru] [-Policies <PolicyObject[]>] [-Precedence <Int32>] [<CommonParameters>]
```
