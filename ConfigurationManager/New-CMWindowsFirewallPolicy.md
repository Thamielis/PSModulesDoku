New-CMWindowsFirewallPolicy
---------------------------




### Synopsis
Creates a new Windows Firewall policy in Configuration Manager.



---


### Description

The New-CMWindowsFirewallPolicy cmdlet creates a configuration policy for Windows Firewall in Configuration Manager.



Windows Firewall allows or denies incoming connections to an IP address. The blocking actions allow or deny incoming traffic based on a network location type. The network location types are: domain, public, and private.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMWindowsFirewallPolicy](Set-CMWindowsFirewallPolicy)





---


### Examples
#### Example 1: Create a Windows Firewall policy
```PowerShell
PS XYZ:\> New-CMWindowsFirewallPolicy -Name "test01" -Description "323132" -DomainTurnOnFirewall Yes -PrivateTurnOnFirewall Yes -PublicTurnOnFirewall Yes
```
This command creates a new Windows Firewall policy and enables the firewall for domain, private, and public network location types.


---


### Parameters
#### **Description**

Specifies a description for the firewall policy.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DomainBlockAllInboundTraffic**

Specifies whether to block all incoming traffic for a domain type of network location.The acceptable values for this parameter are:


* No


* Not Configured


* Yes



Valid Values:

* Yes
* No
* NotConfigured






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SettingType]`|false   |named   |False        |



#### **DomainNotification**





Valid Values:

* Yes
* No
* NotConfigured






|Type           |Required|Position|PipelineInput|Aliases            |
|---------------|--------|--------|-------------|-------------------|
|`[SettingType]`|false   |named   |False        |DomainNotifications|



#### **DomainTurnOnFirewall**

Specifies whether to turn on a firewall for a domain type of network location. The acceptable values for this parameter are:


* No


* Not Configured


* Yes



Valid Values:

* Yes
* No
* NotConfigured






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SettingType]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specifies a name for the firewall policy in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **PrivateBlockAllInboundTraffic**

Specifies whether to block all incoming traffic for a private type of network location. The acceptable values for this parameter are:


* No


* Not Configured


* Yes



Valid Values:

* Yes
* No
* NotConfigured






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SettingType]`|false   |named   |False        |



#### **PrivateNotification**





Valid Values:

* Yes
* No
* NotConfigured






|Type           |Required|Position|PipelineInput|Aliases             |
|---------------|--------|--------|-------------|--------------------|
|`[SettingType]`|false   |named   |False        |PrivateNotifications|



#### **PrivateTurnOnFirewall**

Specifies whether to turn on a firewall for a private type of network location. The acceptable values for this parameter are:


* No


* Not Configured


* Yes



Valid Values:

* Yes
* No
* NotConfigured






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SettingType]`|false   |named   |False        |



#### **PublicBlockAllInboundTraffic**

Specifies whether to block all incoming traffic for a public type of network location. The acceptable values for this parameter are:


* No


* Not Configured


* Yes



Valid Values:

* Yes
* No
* NotConfigured






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SettingType]`|false   |named   |False        |



#### **PublicNotification**





Valid Values:

* Yes
* No
* NotConfigured






|Type           |Required|Position|PipelineInput|Aliases            |
|---------------|--------|--------|-------------|-------------------|
|`[SettingType]`|false   |named   |False        |PublicNotifications|



#### **PublicTurnOnFirewall**

Specifies whether to enable Windows Firewall for a public network location. The acceptable values for this parameter are:


* No


* Not Configured


* Yes



Valid Values:

* Yes
* No
* NotConfigured






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SettingType]`|false   |named   |False        |



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
New-CMWindowsFirewallPolicy [-Description <String>] [-DisableWildcardHandling] [-DomainBlockAllInboundTraffic {Yes | No | NotConfigured}] [-DomainNotification {Yes | No | NotConfigured}] [-DomainTurnOnFirewall {Yes | No | NotConfigured}] [-ForceWildcardHandling] -Name <String> [-PrivateBlockAllInboundTraffic {Yes | No | NotConfigured}] [-PrivateNotification {Yes | No | NotConfigured}] [-PrivateTurnOnFirewall {Yes | No | NotConfigured}] [-PublicBlockAllInboundTraffic {Yes | No | NotConfigured}] [-PublicNotification {Yes | No | NotConfigured}] [-PublicTurnOnFirewall {Yes | No | NotConfigured}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
