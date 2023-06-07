Remove-CMServiceConnectionPoint
-------------------------------




### Synopsis
Removes a service connection point.



---


### Description

The Remove-CMServiceConnectionPoint cmdlet removes a service connection point role from a site system server.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMServiceConnectionPoint](Add-CMServiceConnectionPoint)



* [Get-CMServiceConnectionPoint](Get-CMServiceConnectionPoint)



* [Set-CMServiceConnectionPoint](Set-CMServiceConnectionPoint)





---


### Examples
#### Example 1: Remove a service connection point by name
```PowerShell
PS XYZ:\> Remove-CMServiceConnectionPoint -SiteSystemServerName "SiteSystemServer01.Contoso.com" -SiteCode PS1 -Force
```
This command removes the service connection point role from the site system server named SiteSystemServer01.Contoso.com with the site code PS1. Specifying the Force parameter indicates that the user is not prompted before the service connection point is removed.
#### Example 2: Remove a service connection point by using a variable
```PowerShell
PS XYZ:\> $ConnPoint = Get-CMServiceConnectionPoint -SiteCode PS1 -SiteSystemServerName "SiteSystemServer02.Contoso.com"
PS XYZ:\> Remove-CMServiceConnectionPoint -InputObject $ConnPoint -Force
```
The first command gets the service connection point object for the site system server named SiteSystemServer02.Contoso.com with the site code PS1 and stores the object in the $ConnPoint variable.


The second command removes the service connection point object stored in $ConnPoint. Specifying the Force parameter indicates that the user is not prompted before the service connection point is removed.
#### Example 3: Remove a service connection point by using the pipeline
```PowerShell
PS XYZ:\> Get-CMServiceConnectionPoint -SiteCode PS1 -SiteSystemServerName "SiteSystemServer03.Contoso.com" | Remove-CMServiceConnectionPoint -Force
```
This command gets the service connection point object for the site system server named SiteSystemServer03.Contoso.com with the site code PS1 and uses the pipeline operator to pass the object to Remove-CMServiceConnectionPoint , which removes the service connection point object. Specifying the Force parameter indicates that the user is not prompted before the service connection point is removed.


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

Specifies a service connection point object. To obtain a service connection point object, use the Get-CMServiceConnectionPoint cmdlet.






|Type             |Required|Position|PipelineInput |Aliases              |
|-----------------|--------|--------|--------------|---------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ReportingServicePoint|



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of a site system server that hosts the service connection point role.






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
Remove-CMServiceConnectionPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMServiceConnectionPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
