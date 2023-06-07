Remove-CMFallbackStatusPoint
----------------------------




### Synopsis
Removes a Configuration Manager fallback status point.



---


### Description

The Remove-CMFallbackStatusPoint cmdlet removes a specified fallback status point site system role. You can specify the site system name and site code for a fallback status point or use the Get-CMFallbackStatusPoint cmdlet to obtain a fallback status point object.



Configuration Manager can use one or more fallback status points to collect state messages for a site and send them on to Configuration Manager. After you remove a fallback status point, that system no longer forwards state messages.



The use of a fallback status point is optional. You can use this cmdlet to remove redundant fallback status points or to remove the last fallback status point from a site if you do not want to use that role.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMFallbackStatusPoint](Add-CMFallbackStatusPoint)



* [Get-CMFallbackStatusPoint](Get-CMFallbackStatusPoint)



* [Set-CMFallbackStatusPoint](Set-CMFallbackStatusPoint)





---


### Examples
#### Example 1: Remove a specified fallback status point
```PowerShell
PS XYZ:\> Remove-CMFallbackStatusPoint -SiteCode "CM1" -SiteSystemServerName "Server21.West01.Contoso.com"
```
This command removes the fallback status point for the site with the site code CM1 and the system name Server21.West01.Contoso.com.
#### Example 2: Remove a fallback status point object
```PowerShell
PS XYZ:\> $CMFSP = Get-CMFallbackStatusPoint -SiteCode "CM1" -SiteSystemServerName "Server21.West01.Contoso.com"
PS XYZ:\> Remove-CMFallbackStatusPoint -InputObject $CMFSP
```
The first command gets a fallback status point for the site with the site code CM1 and the system name Server21.West01.Contoso.com and stores that object in the $CMFSP variable.


The second command removes the object stored in $CMFSP.


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

Specifies a fallback status point role. To get a fallback status point role, use the Get-CMFallbackStatusPoint cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|FallbackStatusPoint|



#### **SiteCode**

Specifies the site code for a fallback status point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the site system name for a fallback status point.






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
Remove-CMFallbackStatusPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMFallbackStatusPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
