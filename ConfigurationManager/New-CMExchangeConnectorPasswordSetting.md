New-CMExchangeConnectorPasswordSetting
--------------------------------------




### Synopsis
Add new password settings to a Exchange Server connector in Configuration Manager.



---


### Description

The New-CMExchangeConnectorPasswordSetting cmdlet adds new password settings to a Microsoft Exchange Server connector in Configuration Manager. An Exchange Server connector in Configuration Manager manages mobile devices that connect to an on-premise or online Exchange Server by using the Exchange ActiveSync protocol.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMExchangeConnectorEmailManagementSetting](New-CMExchangeConnectorEmailManagementSetting)



* [New-CMExchangeConnectorSecuritySetting](New-CMExchangeConnectorSecuritySetting)





---


### Examples
#### Example 1: Specify password settings for an Exchange Server connector
```PowerShell
New-CMExchangeConnectorPasswordSetting -PasswordEnabled $True -MinimumPasswordLength 8 -PasswordExpiration 51 -PasswordHistory 21 -WipeAfterFailedAttempt 6 -MaximumIdleTimeMinutes 41 -PasswordComplexity Strong -MinimumComplexChar 3 -AllowSimplePassword $True -PasswordRecovery $True
```



---


### Parameters
#### **AllowSimplePassword**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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



#### **MaximumIdleTimeMins**








|Type     |Required|Position|PipelineInput|Aliases               |
|---------|--------|--------|-------------|----------------------|
|`[Int32]`|false   |named   |False        |MaximumIdleTimeMinutes|



#### **MinimumComplexChar**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MinimumPasswordLength**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PasswordComplexity**





Valid Values:

* Pin
* Strong






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[PasswordComplexityType]`|false   |named   |False        |



#### **PasswordEnabled**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|true    |named   |False        |



#### **PasswordExpiration**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PasswordHistory**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PasswordRecovery**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WipeAfterFailedAttempt**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.HS.ExchangeConnectorPasswordSetting






---


### Notes
Cmdlet aliases: New-CMExchangeServerConnectorPasswordSetting



---


### Syntax
```PowerShell
New-CMExchangeConnectorPasswordSetting [-AllowSimplePassword <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaximumIdleTimeMins <Int32>] [-MinimumComplexChar <Int32>] [-MinimumPasswordLength <Int32>] [-PasswordComplexity {Pin | Strong}] -PasswordEnabled <Boolean> [-PasswordExpiration <Int32>] [-PasswordHistory <Int32>] [-PasswordRecovery <Boolean>] [-WipeAfterFailedAttempt <Int32>] [<CommonParameters>]
```
