New-CMExchangeConnectorApplicationSetting
-----------------------------------------




### Synopsis
Create application-related settings for a mobile device that uses a Exchange Server connector.



---


### Description

The New-CMExchangeConnectorApplicationSetting cmdlet creates application-related settings for a mobile device that uses a Microsoft Exchange Server connector.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMExchangeConnectorAccessRule](New-CMExchangeConnectorAccessRule)



* [New-CMExchangeConnectorEmailManagementSetting](New-CMExchangeConnectorEmailManagementSetting)



* [New-CMExchangeConnectorPasswordSetting](New-CMExchangeConnectorPasswordSetting)



* [New-CMExchangeConnectorSecuritySetting](New-CMExchangeConnectorSecuritySetting)





---


### Examples
#### Example 1: Set application options for an Exchange Server connector
```PowerShell
New-CMExchangeConnectorApplicationSetting -UnsignedApplication $False -UnsignedInstall $True -BlockedApplication "a1","a2"
```



---


### Parameters
#### **BlockedApplication**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



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



#### **UnsignedApplication**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UnsignedInstall**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.HS.ExchangeConnectorApplicationSetting






---


### Notes
Cmdlet aliases: New-CMExchangeServerConnectorApplicationSetting



---


### Syntax
```PowerShell
New-CMExchangeConnectorApplicationSetting [-BlockedApplication <String[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-UnsignedApplication <Boolean>] [-UnsignedInstall <Boolean>] [<CommonParameters>]
```
