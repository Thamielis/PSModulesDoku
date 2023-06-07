New-CMExchangeConnectorSecuritySetting
--------------------------------------




### Synopsis
Configure security options for a Microsoft Exchange Server connector in Configuration Manager.



---


### Description

The New-CMExchangeConnectorSecuritySetting cmdlet configures security options for a Microsoft Exchange Server connector in Configuration Manager. An Exchange Server connector in Configuration Manager manages mobile devices that connect to an on-premises or online Exchange Server by using the Exchange ActiveSync protocol.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMExchangeConnectorAccessRule](New-CMExchangeConnectorAccessRule)



* [New-CMExchangeConnectorApplicationSetting](New-CMExchangeConnectorApplicationSetting)



* [New-CMExchangeConnectorEmailManagementSetting](New-CMExchangeConnectorEmailManagementSetting)



* [New-CMExchangeConnectorPasswordSetting](New-CMExchangeConnectorPasswordSetting)





---


### Examples
#### Example 1: Configure security settings for a mobile device
```PowerShell
PS XYZ:\> New-CMExchangeConnectorSecuritySetting -RemoteDesktop $True -StorageCard $True -Camera $True -Bluetooth $False -WiFiConnection HandsfreeOnly -Infra $False -Browser $False -StorageCardEncrypt $False -FileEncrypt $False -TextMessage $False
```



---


### Parameters
#### **Bluetooth**





Valid Values:

* Disable
* HandsfreeOnly
* Allow






|Type                       |Required|Position|PipelineInput|
|---------------------------|--------|--------|-------------|
|`[BluetoothConnectionType]`|false   |named   |False        |



#### **Browser**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Camera**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileEncrypt**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Infrared**








|Type       |Required|Position|PipelineInput|Aliases|
|-----------|--------|--------|-------------|-------|
|`[Boolean]`|false   |named   |False        |Infra  |



#### **RemoteDesktop**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **StorageCard**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **StorageCardEncrypt**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **TextMessage**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WifiConnection**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.HS.ExchangeConnectorSecuritySetting






---


### Notes
Cmdlet aliases: New-CMExchangeServerConnectorSecuritySetting



---


### Syntax
```PowerShell
New-CMExchangeConnectorSecuritySetting [-Bluetooth {Disable | HandsfreeOnly | Allow}] [-Browser <Boolean>] [-Camera <Boolean>] [-DisableWildcardHandling] [-FileEncrypt <Boolean>] [-ForceWildcardHandling] [-Infrared <Boolean>] [-RemoteDesktop <Boolean>] [-StorageCard <Boolean>] [-StorageCardEncrypt <Boolean>] [-TextMessage <Boolean>] [-WifiConnection <Boolean>] [<CommonParameters>]
```
