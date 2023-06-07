Remove-CMEndpointProtectionPoint
--------------------------------




### Synopsis
Removes an Endpoint Protection point.



---


### Description

The Remove-CMEndpointProtectionPoint cmdlet removes a System Center 2016 Endpoint Protection point from Configuration Manager. For more information about Endpoint Protection in Configuration Manager, see Endpoint Protection in Configuration Manager (/mem/configmgr/protect/deploy-use/endpoint-protection).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Endpoint Protection in Configuration Manager](Endpoint Protection in Configuration Manager)



* [Add-CMEndpointProtectionPoint](Add-CMEndpointProtectionPoint)



* [Get-CMEndpointProtectionPoint](Get-CMEndpointProtectionPoint)



* [Set-CMEndpointProtectionPoint](Set-CMEndpointProtectionPoint)





---


### Examples
#### Example 1: Remove an Endpoint Protection point
```PowerShell
PS XYZ:\> Remove-CMEndpointProtectionPoint -SiteSystemServerName "CMServer01.Contoso.com" -SiteCode "CM1"
```
This command removes an Endpoint Protection point.
#### Example 2: Remove an Endpoint Protection point by using an input object
```PowerShell
PS XYZ:\> $EPP = Get-CMEndpointProtectionPoint -SiteCode "CM1" -SiteSystemServerName "CMServer01.Contoso.com"
PS XYZ:\> Remove-CMEndpointProtectionPoint -InputObject $EPP
```
The first command uses the Get-CMEndpointProtectionPoint cmdlet to get an Endpoint Protection point object and assign it to the variable $EPP.


The second command removes the Endpoint Protection point object that is assigned to the variable $EPP.


---


### Parameters
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



#### **InputObject**

Specifies the input to this cmdlet. To obtain an input object, use the Get-CMEndpointProtectionPoint cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                |
|-----------------|--------|--------|--------------|-----------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|EndpointProtectionPoint|



#### **SiteCode**

Specifies a site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies a fully qualified domain name (FQDN) of the server that hosts the site system role.






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
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMEndpointProtectionPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMEndpointProtectionPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
