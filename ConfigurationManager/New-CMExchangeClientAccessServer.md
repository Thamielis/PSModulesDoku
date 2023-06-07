New-CMExchangeClientAccessServer
--------------------------------




### Synopsis
Creates a Client Access server role for an Exchange Server.



---


### Description

The New-CMExchangeClientAccessServer cmdlet creates a Client Access server role for a Microsoft Exchange Server. The Client Access server role accepts connections to Exchange Server from different types of clients. Software clients such as Microsoft Outlook use POP3 or IMAP4 connections to communicate with Exchange Server. Hardware clients, such as mobile devices, use ActiveSync, POP3, or IMAP4 to communicate with Exchange Server.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Create an Exchange Client Access server
```PowerShell
PS XYZ:\> $Ecs= New-CMExchangeClientAccessServer -ExchangeClientAccessServerName "ContosoWestCAS11" -ActiveDirectorySiteName "ContosoWestAD01"
```
This command creates a new Exchange Client Access server named ContosoWestCAS11 and associates it with the Active Directory site named ContosoWestAD01, then places the resulting Exchange Client Access server object in the variable $Ecs.


---


### Parameters
#### **ActiveDirectorySiteName**

Specifies the name of the Active Directory site on which you are installing the Client Access server role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExchangeClientAccessServerName**

Specifies the name of the Exchange Client Access server that you create.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
* [Collections.Generic.Dictionary`2[[System.String, System.Private.CoreLib, Version=7.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.String, System.Private.CoreLib, Version=7.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]](https://learn.microsoft.com/en-us/dotnet/api/System.Collections.Generic.Dictionary`2[[System.String, System.Private.CoreLib, Version=7.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.String, System.Private.CoreLib, Version=7.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]])






---


### Notes




---


### Syntax
```PowerShell
New-CMExchangeClientAccessServer -ActiveDirectorySiteName <String> [-DisableWildcardHandling] -ExchangeClientAccessServerName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
