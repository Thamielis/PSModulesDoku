Remove-CMManagementPoint
------------------------




### Synopsis
Removes a management point.



---


### Description

The Remove-CMManagementPoint cmdlet removes a management point. A management point is a site system role that provides policy and service location information to clients and receives configuration data from clients.



When you remove a management point, Configuration Manager disables communication between the site server and the clients that you assigned to the site server. Configuration Manager cannot provide these clients with installation prerequisites, client installation files, configuration details, advertisements, and software distribution package source file locations. Additionally, Configuration Manager cannot receive inventory data, software metering information, and status and state messages from the clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMManagementPoint](Add-CMManagementPoint)



* [Get-CMManagementPoint](Get-CMManagementPoint)



* [Get-CMManagementPointComponent](Get-CMManagementPointComponent)





---


### Examples
#### Example 1: Remove a management point
```PowerShell
PS XYZ:\> Remove-CMManagementPoint -SiteSystemServerName "cmcen-dist02.tsqa.contoso.com" -SiteCode "CM1"
```
This command removes the management point from the Configuration Manager site that has the site code CM1 on the site system named cmcen-dist02.tsqa.contoso.com.
#### Example 2: Remove a management point by using an object variable
```PowerShell
PS XYZ:\> $Mp = Get-CMManagementPoint -SiteSystemServerName "dist02.tsqa.contoso.com" -SiteCode "CM1"
PS XYZ:\> Remove-CMManagementPoint -InputObject $Mp
```
The first command gets the management point from the Configuration Manager site that has the site code CM1 on the site system named dist02.tsqa.contoso.com. The command stores the results in the $Mp variable.


The second command removes the management point stored in the $Mp variable.


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

Specifies a CMManagementPoint object. To obtain a CMManagementPoint object, use the Get-CMManagementPoint (Get-CMManagementPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ManagementPoint|



#### **SiteCode**

Specifies the site code of the Configuration Manager site that hosts the site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the fully qualified domain name (FQDN) of the server that hosts the site system role.






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
Remove-CMManagementPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMManagementPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
