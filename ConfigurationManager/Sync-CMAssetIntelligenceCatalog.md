Sync-CMAssetIntelligenceCatalog
-------------------------------




### Synopsis
Synchronizes the Asset Intelligence catalog with System Center Online.



---


### Description

The Sync-CMAssetIntelligenceCatalog cmdlet synchronizes the local Asset Intelligence catalog with System Center Online to retrieve the latest software title categorization. The Asset Intelligence catalog contains categorization and identification information for software titles. System Center Online accepts only one manual synchronization request in a 12-hour period.



Configuration Manager updates the asset Intelligence catalog by using the Asset Intelligence synchronization point site system role. You must install an Asset Intelligence synchronization point site system role before you can synchronize the Asset Intelligence catalog with System Center Online. You can use the Add-CMAssetIntelligenceSynchronizationPoint cmdlet to install an Asset Intelligence synchronization point site system role.



When you manually request catalog synchronization with System Center Online, it could take 15 minutes or longer to complete the synchronization process with System Center Online.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMAssetIntelligenceSynchronizationPoint](Add-CMAssetIntelligenceSynchronizationPoint)



* [Get-CMAssetIntelligenceSynchronizationPoint](Get-CMAssetIntelligenceSynchronizationPoint)



* [Send-CMAssetIntelligenceCatalogUpdateRequest](Send-CMAssetIntelligenceCatalogUpdateRequest)



* [Set-CMAssetIntelligenceSynchronizationPoint](Set-CMAssetIntelligenceSynchronizationPoint)





---


### Examples
#### Example 1: Update the Asset Intelligence catalog
```PowerShell
PS XYZ:\> Sync-CMAssetIntelligenceCatalog -SiteCode "CM2" -SiteSystemServerName "Contoso-west02"
```
This command the updates the Asset Intelligence catalog on the Configuration Manager site that has the site code CM2 on the site system server named Contoso-west02.


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
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Sync-CMAssetIntelligenceCatalog [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
