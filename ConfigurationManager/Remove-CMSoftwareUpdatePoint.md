Remove-CMSoftwareUpdatePoint
----------------------------




### Synopsis
Remove a software update point.



---


### Description

Use this cmdlet to remove a software update point site system role.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMSoftwareUpdatePoint](Add-CMSoftwareUpdatePoint)



* [Get-CMSoftwareUpdatePoint](Get-CMSoftwareUpdatePoint)



* [Set-CMSoftwareUpdatePoint](Set-CMSoftwareUpdatePoint)





---


### Examples
#### Example 1: Remove a software update point by name
```PowerShell
Remove-CMSoftwareUpdatePoint -SiteCode "CM1" -SiteSystemServerName "UpdateSystem.Western.Contoso.com"
```

#### Example 2: Remove a software update point by using a variable
```PowerShell
$CMSUP = Get-CMSoftwareUpdatePoint -SiteCode "CM1" -SiteSystemServerName "UpdateSystem.Western.Contoso.com"

Remove-CMSoftwareUpdatePoint -InputObject $CMSUP -Force
```



---


### Parameters
#### **DefaultServerName**

Specify the FQDN of the default software update point.






|Type      |Required|Position|PipelineInput|Aliases                             |
|----------|--------|--------|-------------|------------------------------------|
|`[String]`|false   |named   |False        |DefaultSoftwareUpdatePointServerName|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Add this parameter to run the cmdlet without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a software update point object to remove. To get this object, use the Get-CMSoftwareUpdatePoint (Get-CMSoftwareUpdatePoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SoftwareUpdatePoint|



#### **SiteCode**

Specify the three-character code for the site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the name of a server that hosts the software update point.






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
Remove-CMSoftwareUpdatePoint [-DefaultServerName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdatePoint [-SiteSystemServerName] <String> [-DefaultServerName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
