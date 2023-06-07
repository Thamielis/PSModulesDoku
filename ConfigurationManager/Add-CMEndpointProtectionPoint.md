Add-CMEndpointProtectionPoint
-----------------------------




### Synopsis
Adds a site system role for Endpoint Protection.



---


### Description

The Add-CMEndpointProtectionPoint cmdlet adds a site system role for System Center 2016 Endpoint Protection to a Configuration Manager site.



Endpoint Protection lets you manage antimalware policies and Windows Firewall security for client computers in Configuration Manager. In order to use Endpoint Protection with Configuration Manager, you must install a single site system role for Endpoint Protection, either in the central site or in a stand-alone primary site. For more information about Endpoint Protection in Configuration Manager, see Endpoint Protection in Configuration Manager (/mem/configmgr/protect/deploy-use/endpoint-protection).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Endpoint Protection in Configuration Manager](Endpoint Protection in Configuration Manager)



* [Get-CMEndpointProtectionPoint](Get-CMEndpointProtectionPoint)



* [Remove-CMEndpointProtectionPoint](Remove-CMEndpointProtectionPoint)



* [Set-CMEndpointProtectionPoint](Set-CMEndpointProtectionPoint)





---


### Examples
#### Example 1: Add a site system role
```PowerShell
PS XYZ:\>Add-CMEndpointProtectionPoint -LicenseAgreed $True -ProtectionService BasicMembership -SiteCode "CM1" -SiteSystemServerName "CMEPPoint.Western.Contoso.com"
```
This command adds an Endpoint Protection point for the site that has the site code CM1. The specified computer hosts the role. The command also specifies that you accept the terms of the license agreement and have a basic membership for Endpoint Protection.


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

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteServer|



#### **LicenseAgreed**

Specifies whether you agree to the Endpoint Protection software licensing terms.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ProtectionService**

Specifies the type of membership you have for Microsoft Active Protection Service (MAPS). Valid values are:


* AdvancedMembership


* BasicMembership


* DoNotJoinMaps



Valid Values:

* DoNotJoinMaps
* BasicMembership
* AdvancedMembership






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[MapsMembershipType]`|true    |named   |False        |



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of a server that hosts a site system role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



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
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Add-CMEndpointProtectionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-LicenseAgreed <Boolean>] -ProtectionService {DoNotJoinMaps | BasicMembership | AdvancedMembership} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMEndpointProtectionPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-LicenseAgreed <Boolean>] -ProtectionService {DoNotJoinMaps | BasicMembership | AdvancedMembership} [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
