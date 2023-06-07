Set-CMManagementPointComponent
------------------------------




### Synopsis
Sets a component for a management point in Configuration Manager.



---


### Description

The Set-CMManagementPointComponent cmdlet sets a component for a management point in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMManagementPointComponent](Get-CMManagementPointComponent)





---


### Examples
#### Example 1: Set a management point component
```PowerShell
PS XYZ:\> Set-CMManagementPointComponent -SiteCode "CM1" -PublishDNS $True
```
The command sets a management point component by using the SiteCode parameter. The command also sets the PublishDNS parameter to $True to publish the management point component in DNS.


---


### Parameters
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



#### **InputObject**

Specifies an input object. To obtain an input object, use the Get-CMManagementPointComponent (Get-CMManagementPointComponent.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteName|



#### **PublishDns**

Indicates whether to publish  resource records for the management point component in the Domain Name System (DNS). Configuration Manager clients use DNS service location resource records (SRV RR) to find a management point in a site.


For Configuration Manager to publish management points to DNS, your DNS servers must have version 8.1.2 of BIND, or later. Your DNS servers must be configured for automatic updates and support service location resource records. The fully qualified domain names (FQDNs) of management points must have host entries in DNS.


You must assign clients to a specific site and configure the clients to use the site code with the domain suffix of their management point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SiteCode**

Specifies a site code in Configuration Manager.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMManagementPointComponent [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PublishDns <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMManagementPointComponent [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PublishDns <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMManagementPointComponent [-DisableWildcardHandling] [-ForceWildcardHandling] [-PublishDns <Boolean>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
