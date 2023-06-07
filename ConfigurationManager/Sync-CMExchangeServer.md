Sync-CMExchangeServer
---------------------




### Synopsis
Synchronizes Configuration Manager mobile device information with an Exchange Server.



---


### Description

The Sync-CMExchangeServer cmdlet synchronizes mobile device information with a specified Microsoft Exchange Server for one or more Configuration Manager sites.



Configuration Manager works with Exchange Server to manage mobile devices that cannot run Configuration Manager clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMExchangeServer](Get-CMExchangeServer)



* [New-CMExchangeServer](New-CMExchangeServer)



* [Remove-CMExchangeServer](Remove-CMExchangeServer)



* [Set-CMExchangeServer](Set-CMExchangeServer)





---


### Examples
#### Example 1: Synchronize with an nextref_exchange
```PowerShell
PS XYZ:\> Sync-CMExchangeServer -Address "https://localhost/PowerShell" -SiteCode "PE1"
```
This command synchronizes mobile devices for the site that has the site code PE1 with the specified Exchange Server.


---


### Parameters
#### **Address**

Specifies a URL for the Exchange Server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
None





---


### Outputs
* IResultObject#SMS_SCI_Component






---


### Notes




---


### Syntax
```PowerShell
Sync-CMExchangeServer -Address <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-PassThru] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
