Set-CMWindowsFirewallPolicy
---------------------------




### Synopsis
Changes settings of a Windows Firewall policy.



---


### Description

The Set-CMWindowsFirewallPolicy cmdlet changes settings of one or more Windows Firewall policies for System Center 2016 Endpoint Protection in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMWindowsFirewallPolicy](New-CMWindowsFirewallPolicy)





---


### Examples
#### Example 1: Decrease the priority of a Windows Firewall policy by using a name
```PowerShell
PS XYZ:\> Set-CMWindowsFirewallPolicy -Priority Decrease -Name "WFPContoso01"
```
This command decreases the priority of the Windows Firewall policy named WFPContoso01.
#### Example 2: Decrease the priority of a Windows Firewall policy by using an ID
```PowerShell
PS XYZ:\> Set-CMWindowsFirewallPolicy -Priority Decrease -Id "16777568"
```
This command decreases the priority of the Windows Firewall policy that has the ID 16777568.
#### Example 3: Increase the priority of a Windows Firewall policy by using an object variable
```PowerShell
PS XYZ:\> $WFPobj=Get-CMWindowsFirewallPolicy -Id "16777568"
PS XYZ:\> Set-CMWindowsFirewallPolicy -Priority Increase -InputObject $WFPobj
```
The first command gets the CMWindowsFirewallPolicy object that has the ID 16777568 and stores it in the $WFPobj variable.


The second command increases the priority of the Windows Firewall policy stored in the $WFPobj variable.


---


### Parameters
#### **Description**

Specifies a description for the Windows Firewall policy.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



#### **Digest**








|Type                 |Required|Position|PipelineInput |
|---------------------|--------|--------|--------------|
|`[ConfigurationItem]`|false   |named   |True (ByValue)|



#### **DigestPath**








|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|false   |named   |False        |DesiredConfigurationDigestPath|



#### **DigestXml**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DomainBlockAllInboundTraffic**

Specifies whether the firewall blocks all incoming traffic for a domain type network location. Valid values are:


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

Specifies whether to enable Windows Firewall for domain network location. Valid values are:


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



#### **Id**

Specifies an array of IDs of firewall policies.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a CMWindowsFirewallPolicy object. To obtain a CMWindowsFirewallPolicy object, use the Get-CMWindowsFirewallPolicy (Get-CMWindowsFirewallPolicy.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies an array of firewall policy names.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **NewName**

Specifies a new name for the firewall policy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Order**

{{ Fill Order Description }}



Valid Values:

* Increase
* Decrease






|Type                  |Required|Position|PipelineInput|Aliases |
|----------------------|--------|--------|-------------|--------|
|`[PriorityChangeType]`|true    |named   |False        |Priority|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PrivateBlockAllInboundTraffic**

Specifies whether the firewall blocks all incoming traffic for a private network location. Valid values are:


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

Specifies whether to enable Windows Firewall for a private network location. Valid values are:


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

Specifies whether the firewall blocks all incoming traffic for a public network location. Valid values are:


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

Specifies whether to enable Windows Firewall for a public network location. Valid values are:


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
Microsoft.ConfigurationManagement.DesiredConfigurationManagement.ConfigurationItem



Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMWindowsFirewallPolicy [-InputObject] <IResultObject> [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-DomainBlockAllInboundTraffic {Yes | No | NotConfigured}] [-DomainNotification {Yes | No | NotConfigured}] [-DomainTurnOnFirewall {Yes | No | NotConfigured}] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-PrivateBlockAllInboundTraffic {Yes | No | NotConfigured}] [-PrivateNotification {Yes | No | NotConfigured}] [-PrivateTurnOnFirewall {Yes | No | NotConfigured}] [-PublicBlockAllInboundTraffic {Yes | No | NotConfigured}] [-PublicNotification {Yes | No | NotConfigured}] [-PublicTurnOnFirewall {Yes | No | NotConfigured}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMWindowsFirewallPolicy [-Id] <Int32> [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-DomainBlockAllInboundTraffic {Yes | No | NotConfigured}] [-DomainNotification {Yes | No | NotConfigured}] [-DomainTurnOnFirewall {Yes | No | NotConfigured}] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-PrivateBlockAllInboundTraffic {Yes | No | NotConfigured}] [-PrivateNotification {Yes | No | NotConfigured}] [-PrivateTurnOnFirewall {Yes | No | NotConfigured}] [-PublicBlockAllInboundTraffic {Yes | No | NotConfigured}] [-PublicNotification {Yes | No | NotConfigured}] [-PublicTurnOnFirewall {Yes | No | NotConfigured}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMWindowsFirewallPolicy [-Name] <String> [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-DomainBlockAllInboundTraffic {Yes | No | NotConfigured}] [-DomainNotification {Yes | No | NotConfigured}] [-DomainTurnOnFirewall {Yes | No | NotConfigured}] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-PrivateBlockAllInboundTraffic {Yes | No | NotConfigured}] [-PrivateNotification {Yes | No | NotConfigured}] [-PrivateTurnOnFirewall {Yes | No | NotConfigured}] [-PublicBlockAllInboundTraffic {Yes | No | NotConfigured}] [-PublicNotification {Yes | No | NotConfigured}] [-PublicTurnOnFirewall {Yes | No | NotConfigured}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMWindowsFirewallPolicy [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -Order {Increase | Decrease} [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMWindowsFirewallPolicy [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -Order {Increase | Decrease} [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMWindowsFirewallPolicy [-Name] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -Order {Increase | Decrease} [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
