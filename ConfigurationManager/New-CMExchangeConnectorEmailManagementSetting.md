New-CMExchangeConnectorEmailManagementSetting
---------------------------------------------




### Synopsis
Create a set of email management settings for a mobile device that uses an Exchange Server connector.



---


### Description

The New-CMExchangeConnectorEmailManagementSetting cmdlet creates a set of e-mail management settings for a mobile device that uses an Exchange Server connector.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMExchangeConnectorAccessRule](New-CMExchangeConnectorAccessRule)



* [New-CMExchangeConnectorApplicationSetting](New-CMExchangeConnectorApplicationSetting)



* [New-CMExchangeConnectorPasswordSetting](New-CMExchangeConnectorPasswordSetting)



* [New-CMExchangeConnectorSecuritySetting](New-CMExchangeConnectorSecuritySetting)





---


### Examples
#### Example 1: Add email management settings to a mobile device
```PowerShell
New-CMExchangeConnectorEmailManagementSetting -AllowHtmlEmail $True -ConsumerEmail $True -EmailAttachmentPolicy $True -MaximumCalenderAge ThreeMonths -MaximumEmailAge OneDay -PushWhenRoaming $True -MaximumSizeAttachment 24 -MaximumSizeHtmlEmail 402 -MaximumSizeTextEmail 401
```



---


### Parameters
#### **AllowHtmlEmail**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ConsumerEmail**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EmailAttachmentPolicy**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **MaximumCalendarAge**





Valid Values:

* All
* TwoWeeks
* OneMonth
* ThreeMonths
* SixMonths






|Type                  |Required|Position|PipelineInput|Aliases           |
|----------------------|--------|--------|-------------|------------------|
|`[MaxCalendarAgeType]`|false   |named   |False        |MaximumCalenderAge|



#### **MaximumEmailAge**





Valid Values:

* All
* OneDay
* ThreeDays
* OneWeek
* TwoWeeks
* OneMonth






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[MaxEmailAgeType]`|false   |named   |False        |



#### **MaximumSizeAttachment**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MaximumSizeHtmlEmail**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MaximumSizeTextEmail**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PushWhenRoaming**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.HS.ExchangeConnectorEmailManagementSetting






---


### Notes
Cmdlet aliases: New-CMExchangeServerConnectorEmailManagementSetting



---


### Syntax
```PowerShell
New-CMExchangeConnectorEmailManagementSetting [-AllowHtmlEmail <Boolean>] [-ConsumerEmail <Boolean>] [-DisableWildcardHandling] [-EmailAttachmentPolicy <Boolean>] [-ForceWildcardHandling] [-MaximumCalendarAge {All | TwoWeeks | OneMonth | ThreeMonths | SixMonths}] [-MaximumEmailAge {All | OneDay | ThreeDays | OneWeek | TwoWeeks | OneMonth}] [-MaximumSizeAttachment <Int32>] [-MaximumSizeHtmlEmail <Int32>] [-MaximumSizeTextEmail <Int32>] [-PushWhenRoaming <Boolean>] [<CommonParameters>]
```
