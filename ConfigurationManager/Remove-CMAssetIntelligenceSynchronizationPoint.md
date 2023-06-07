Remove-CMAssetIntelligenceSynchronizationPoint
----------------------------------------------




### Synopsis
Removes an Asset Intelligence synchronization point.



---


### Description

The Remove-CMAssetIntelligenceSynchronizationPoint cmdlet removes an Asset Intelligence synchronization point from a site system. After you remove an Asset Intelligence synchronization point, the Configuration Manager sites that used the synchronization point cannot connect to System Center Online.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMAssetIntelligenceSynchronizationPoint](Add-CMAssetIntelligenceSynchronizationPoint)



* [Get-CMAssetIntelligenceSynchronizationPoint](Get-CMAssetIntelligenceSynchronizationPoint)



* [Set-CMAssetIntelligenceSynchronizationPoint](Set-CMAssetIntelligenceSynchronizationPoint)





---


### Examples
#### Example 1: Remove an Asset Intelligence synchronization point
```PowerShell
PS XYZ:\> Remove-CMAssetIntelligenceSynchronizationPoint -SiteSystemServerName "CMDIV-WEST04.CORP.CONTOSO.COM" -SiteCode "CM1"
```
This command removes the Asset Intelligence synchronization point on the Configuration Manager site that has the site code CM1 on the site system server named CMDIV-WEST04.CORP.CONTOSO.COM.
#### Example 2: Remove an Asset Intelligence synchronization point by using an object variable
```PowerShell
PS XYZ:\> $AIsync = Get-CMAssetIntelligenceSynchronizationPoint -SiteSystemServerName "WEST04.CORP.CONTOSO.COM" -SiteCode "ST1"
PS XYZ:\> Remove-CMAssetIntelligenceSynchronizationPoint -InputObject $AIsync
```
The first command gets the Asset Intelligence synchronization point on the Configuration Manager site that has the site code ST1 on the site system server named CMDIV-WEST04.CORP.CONTOSO.COM. The command stores the results in the $AIsync variable.


The second command removes the Asset Intelligence synchronization point stored in the $AIsync variable.


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

Specifies an Asset Intelligence synchronization point object. To get a CMAssetIntelligenceSynchronizationPoint object, use the Get-CMAssetIntelligenceSynchronizationPoint cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SiteCode**

Specifies the three-letter site code of the Configuration Manager site that hosts the site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies an array of fully qualified domain names (FQDN) of the servers that host the site system role.






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
Remove-CMAssetIntelligenceSynchronizationPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAssetIntelligenceSynchronizationPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
