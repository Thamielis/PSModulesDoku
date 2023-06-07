New-CMExchangeConnectorAccessRule
---------------------------------




### Synopsis
Configure access settings for a mobile device that uses a Microsoft Exchange Server connector.



---


### Description

The New-CMExchangeConnectorAccessRule cmdlet configures access settings for a mobile device that uses a Microsoft Exchange Server connector.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMExchangeConnectorApplicationSetting](New-CMExchangeConnectorApplicationSetting)



* [New-CMExchangeConnectorEmailManagementSetting](New-CMExchangeConnectorEmailManagementSetting)



* [New-CMExchangeConnectorPasswordSetting](New-CMExchangeConnectorPasswordSetting)



* [New-CMExchangeConnectorSecuritySetting](New-CMExchangeConnectorSecuritySetting)





---


### Examples
#### Example 1: Configure email management settings for a mobile device
```PowerShell
New-CMExchangeConnectorAccessRule -RuleName "AccessRule01" -AccessLevel Allow -Device DeviceType
```



---


### Parameters
#### **AccessLevel**





Valid Values:

* Allow
* Block
* Quarantine






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[AccessLevelType]`|true    |named   |False        |



#### **Device**





Valid Values:

* DeviceType
* DeviceModel






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[DeviceType]`|true    |named   |False        |



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



#### **RuleName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.HS.ExchangeConnectorAccessRule






---


### Notes
Cmdlet aliases: New-CMExchangeServerConnectorAccessRule



---


### Syntax
```PowerShell
New-CMExchangeConnectorAccessRule -AccessLevel {Allow | Block | Quarantine} -Device {DeviceType | DeviceModel} [-DisableWildcardHandling] [-ForceWildcardHandling] -RuleName <String> [<CommonParameters>]
```
