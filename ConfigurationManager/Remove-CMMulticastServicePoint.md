Remove-CMMulticastServicePoint
------------------------------




### Synopsis
Removes a multicast service point.



---


### Description

The Remove-CMMulticastServicePoint cmdlet removes the multicast service point and disables multicast for the distribution point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMMulticastServicePoint](Add-CMMulticastServicePoint)



* [Get-CMMulticastServicePoint](Get-CMMulticastServicePoint)



* [Set-CMMulticastServicePoint](Set-CMMulticastServicePoint)





---


### Examples
#### Example 1: Remove a multicast service point by using the pipeline
```PowerShell
PS XYZ:\> Get-CMMulticastServicePoint -SiteSystemServerName "server1.contoso.com" -SiteCode "PS1" | Remove-CMMulticastServicePoint -RemoveWds -Force
```
This command gets the multicast service point object with the site system server name of server1.contoso.com and site code PS1 and uses the pipeline operator to pass the object to Remove-CMMulticastServicePoint , which removes the multicast service point and WDS. Using the Force parameter indicates that the user is not prompted for confirmation before the command runs.
#### Example 2: Remove a multicast service point
```PowerShell
PS XYZ:\> Remove-CMMulticastServicePoint -SiteSystemServerName "server1.contoso.com" -SiteCode "PS1" -RemoveWds -Force
```
This command removes the multicast service point with the site system server name of server1.contoso.com and site code PS1. The command removes WDS, and by specifying the Force parameter, does not prompt the user for confirmation before the command runs.


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

Specifies a multicast service point object. To obtain a multicast service point object, use the Get-CMMulticastServicePoint cmdlet.






|Type             |Required|Position|PipelineInput |Aliases              |
|-----------------|--------|--------|--------------|---------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|MulticastServicePoint|



#### **RemoveWds**

Indicates that Windows Deployment Services (WDS) is removed. WDS cannot be removed if the PXE role is still present on the distribution point. The default is to remove WDS.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code for the Configuration Manager site that hosts the site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of the server that hosts a site system role.






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
Remove-CMMulticastServicePoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-RemoveWds] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMMulticastServicePoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RemoveWds] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
