Set-CMEndpointProtectionPoint
-----------------------------




### Synopsis
Modifies a site system role for Endpoint Protection.



---


### Description

The Set-CMEndpointProtectionPoint cmdlet modifies a site system role for System Center 2016 Endpoint Protection in Configuration Manager.



Endpoint Protection lets you manage antimalware policies and Windows Firewall security for client computers in Configuration Manager. In order to use Endpoint Protection with Configuration Manager, you must install a single site system role for Endpoint Protection, either in the central site or in a stand-alone primary site. For more information about Endpoint Protection in Configuration Manager, see the Endpoint Protection in Configuration Manager (/mem/configmgr/protect/deploy-use/endpoint-protection).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Endpoint Protection in Configuration Manager](Endpoint Protection in Configuration Manager)



* [Add-CMEndpointProtectionPoint](Add-CMEndpointProtectionPoint)



* [Get-CMEndpointProtectionPoint](Get-CMEndpointProtectionPoint)



* [Remove-CMEndpointProtectionPoint](Remove-CMEndpointProtectionPoint)





---


### Examples
#### Example 1: Set an endpoint protection point
```PowerShell
PS XYZ:\> Set-CMEndpointProtectionPoint -SiteSystemServerName "CM-Contoso.Contoso.Com" -SiteCode "CM2" -ProtectionService AdvancedMembership
```
The command sets the endpoint protection point for the server, and specifies the membership type for the ProtectionService parameter.
#### Example 2: Set an endpoint protection point by using an input object
```PowerShell
PS XYZ:\> $Epp = Get-CMEndpointProtectionPoint -SiteSystemServerName "CM-Contoso.Contoso.Com" -SiteCode "CM2"
PS XYZ:\> Set-CMEndpointProtectionPoint -InputObject $Epp -ProtectionService BasicMembership
```
The first command uses the Get-CMEndpointProtectionPoint cmdlet to get an endpoint protection point, and stores the result in the $Epp variable.


The second command sets the endpoint protection point for the server by using the input object from the previous command.


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

Specifies an input object. To obtain an input object, use the Get-CMEndpointProtectionPoint (Get-CMEndpointProtectionPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                |
|-----------------|--------|--------|--------------|-----------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|EndpointProtectionPoint|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ProtectionService**

Specifies the type of membership to set for Microsoft Active Protection Service (MAPS). The acceptable values for this parameter are:


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
Set-CMEndpointProtectionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] -ProtectionService {DoNotJoinMaps | BasicMembership | AdvancedMembership} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMEndpointProtectionPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -ProtectionService {DoNotJoinMaps | BasicMembership | AdvancedMembership} [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
