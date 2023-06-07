New-CMRemoteConnectionProfileConfigurationItem
----------------------------------------------




### Synopsis
Creates a remote connection profile.



---


### Description

The New-CMRemoteConnectionProfileConfigurationItem cmdlet creates a remote connection profile. Client computers use remote connection profiles to remotely connect to computers from outside the domain or over the Internet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMRemoteConnectionProfileConfigurationItem](Set-CMRemoteConnectionProfileConfigurationItem)





---


### Examples
#### Example 1: Create a remote connection profile configuration item
```PowerShell
PS XYZ:\> New-CMRemoteConnectionProfileConfigurationItem -Name "EuropeanRemoteConnections" -EnablePrimaryUsers $True -EnableTSConnection $True -EnableTSFirewallRule $True
```
This command creates a remote connection profile configuration item named EuropeanRemoteConnections. For this item the EnablePrimaryUsers , EnableTSConnection , and EnableTSFirewall properties are all set to $True.


---


### Parameters
#### **Description**

Specifies a description for a remote connection profile.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Enable**








|Type       |Required|Position|PipelineInput|Aliases                 |
|-----------|--------|--------|-------------|------------------------|
|`[Boolean]`|false   |named   |False        |EnableConnectionSettings|



#### **EnableNla**

Indicates whether to allow connections only from computers that run Remote Desktop by using Network Level Authentication.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnablePrimaryUser**








|Type       |Required|Position|PipelineInput|Aliases           |
|-----------|--------|--------|-------------|------------------|
|`[Boolean]`|false   |named   |False        |EnablePrimaryUsers|



#### **EnableTSConnection**

Indicates whether to allow remote connections to client computers. If you specify a value for this parameter, you must specify values for the EnablePrimaryUsers and EnableTSFirewallRule parameters.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableTSFirewallRule**

Indicates whether to allow Windows Firewall exceptions for connections in Windows domains and on private networks. If you specify a value for this parameter, you must specify values for the EnablePrimaryUsers and EnableTSConnections parameters.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specifies a name for a remote connection profile.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **RDGatewayServer**

Specifies the host name and port of the Remote Desktop gateway server, for example, Boston.gateway.Contoso.com:8080.






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
* IResultObject#SMS_ConfigurationPolicy






---


### Notes




---


### Syntax
```PowerShell
New-CMRemoteConnectionProfileConfigurationItem [-Description <String>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableNla <Boolean>] [-EnablePrimaryUser <Boolean>] [-EnableTSConnection <Boolean>] [-EnableTSFirewallRule <Boolean>] [-ForceWildcardHandling] -Name <String> [-RDGatewayServer <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
