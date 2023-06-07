Remove-CMEnrollmentProxyPoint
-----------------------------




### Synopsis
Removes an enrollment proxy point.



---


### Description

The Remove-CMEnrollmentProxyPoint cmdlet removes an enrollment proxy point in Configuration Manager. An enrollment proxy point is a site system role that manages enrollment requests from mobile devices. After you remove an enrollment proxy point, mobile devices must use a different enrollment proxy point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMEnrollmentProxyPoint](Add-CMEnrollmentProxyPoint)



* [Get-CMEnrollmentProxyPoint](Get-CMEnrollmentProxyPoint)





---


### Examples
#### Example 1: Remove an enrollment proxy point
```PowerShell
PS XYZ:\> Remove-CMEnrollmentProxyPoint -SiteCode "CM1" -SiteSystemServerName "SiteServer01.Contoso.com"
```
This command removes an enrollment proxy point.


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

Specifies the input to this cmdlet. You can get an input object by using the Get-CMEnrollmentProxyPoint cmdlet.






|Type             |Required|Position|PipelineInput |Aliases             |
|-----------------|--------|--------|--------------|--------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|EnrollmentProxyPoint|



#### **SiteCode**

Specifies a site code.






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
Remove-CMEnrollmentProxyPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMEnrollmentProxyPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
