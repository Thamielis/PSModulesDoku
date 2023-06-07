Remove-CMDistributionPoint
--------------------------




### Synopsis
Removes a distribution point.



---


### Description

The Remove-CMDistributionPoint cmdlet removes a distribution point. When you remove a distribution point, you remove the designation of a site system server to function as a distribution center for content files for applications, packages, software updates, and operating system deployment.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDistributionPoint](Add-CMDistributionPoint)



* [Get-CMDistributionPoint](Get-CMDistributionPoint)



* [New-CMDistributionPointGroup](New-CMDistributionPointGroup)



* [Set-CMDistributionPoint](Set-CMDistributionPoint)



* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)



* [Update-CMDistributionPoint](Update-CMDistributionPoint)





---


### Examples
#### Example 1: Remove a distribution point by using the pipeline
```PowerShell
PS XYZ:\> Get-CMDistributionPoint -SiteSystemServerName "MySiteSys_11310.Contoso.com" | Remove-CMDistributionPoint -Force
```
This command gets the distribution point object for the site system server named MySiteSys_11310.Contoso.com and uses the pipeline operator to pass the object to Remove-CMDistributionPoint , which removes the distribution point object. Specifying the Force parameter indicates that the user is not prompted before the distribution point is removed.
#### Example 2: Remove a distribution point by using an object variable
```PowerShell
PS XYZ:\> $DP = Get-CMDistributionPoint -SiteSystemServerName "MySiteSys_11310.Contoso.com"
PS XYZ:\> Remove-CMDistributionPoint -InputObject $DP -Force
```
The first command gets the distribution point object for the site system server named MySiteSys_11310.Contoso.com and stores the object in the $DP variable.


The second command removes the distribution point stored in $DP. Specifying the Force parameter indicates that the user is not prompted before the distribution point is removed.


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

Specifies a distribution point object. To obtain a distribution point object, use the Get-CMDistributionPoint (Get-CMDistributionPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases          |
|-----------------|--------|--------|--------------|-----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DistributionPoint|



#### **SiteCode**

Specifies the site code for the Configuration Manager site that hosts this site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the FQDN of the server that hosts the site system role.






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
Remove-CMDistributionPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
