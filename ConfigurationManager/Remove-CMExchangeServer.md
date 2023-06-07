Remove-CMExchangeServer
-----------------------




### Synopsis
Removes an Exchange Server object from Configuration Manager.



---


### Description

The Remove-CMExchangeServer cmdlet removes a Microsoft Exchange Server object from Configuration Manager for one or more Configuration Manager sites. This cmdlet does not uninstall the Exchange Server.



Configuration Manager works with Exchange Server to manage mobile devices that cannot run Configuration Manager clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMExchangeServer](Get-CMExchangeServer)



* [New-CMExchangeServer](New-CMExchangeServer)



* [Set-CMExchangeServer](Set-CMExchangeServer)



* [Sync-CMExchangeServer](Sync-CMExchangeServer)





---


### Examples
#### Example 1: Remove an nextref_exchange
```PowerShell
PS XYZ:\> Remove-CMExchangeServer -Address "https://localhost/PowerShell" -SiteCode "PE1"
```
This command removes the Exchange Server with the specified address for the site code PE1.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExchangeServerUrl**








|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|true    |named   |False        |Address<br/>ServerAddress|



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type                 |Required|Position|PipelineInput |
|---------------------|--------|--------|--------------|
|`[ExchangeConnector]`|true    |named   |True (ByValue)|



#### **SiteCode**

Specifies the site code for a Configuration Manager site associated with the Exchange Server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.HS.Types.ExchangeConnector





---


### Outputs
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMExchangeServer [-DisableWildcardHandling] -ExchangeServerUrl <String> [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMExchangeServer [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <ExchangeConnector> [-Confirm] [-WhatIf] [<CommonParameters>]
```
