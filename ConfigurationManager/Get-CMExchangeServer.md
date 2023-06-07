Get-CMExchangeServer
--------------------




### Synopsis
Gets a Configuration Manager Exchange Server object.



---


### Description

The Get-CMExchangeServer cmdlet gets an object that represents a Microsoft Exchange Server that Configuration Manager uses.



Configuration Manager works with Exchange Server to manage mobile devices that cannot run Configuration Manager clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMExchangeServer](New-CMExchangeServer)



* [Remove-CMExchangeServer](Remove-CMExchangeServer)



* [Set-CMExchangeServer](Set-CMExchangeServer)



* [Sync-CMExchangeServer](Sync-CMExchangeServer)





---


### Examples
#### Example 1: Get all Exchange Server systems
```PowerShell
PS XYZ:\> Get-CMExchangeServer
```
This command gets all the Exchange Server items for a Configuration Manager server.
#### Example 2: Get an Exchange Server for a site
```PowerShell
PS XYZ:\> Get-CMExchangeServer -SiteCode "PE1"
```
This command gets an Exchange Server for the site identified by the site code PE1.
#### Example 3: Get a specified nextref_exchange
```PowerShell
PS XYZ:\> Get-CMExchangeServer -Address "https://localhost/PowerShell"
```
This command gets the Exchange Server with the specified address.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExchangeServerUrl**








|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Address|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code for a Configuration Manager site associated with the Exchange Server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* ExchangeConnector[]


* ExchangeConnector






---


### Notes




---


### Syntax
```PowerShell
Get-CMExchangeServer [-DisableWildcardHandling] [-ExchangeServerUrl <String>] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
