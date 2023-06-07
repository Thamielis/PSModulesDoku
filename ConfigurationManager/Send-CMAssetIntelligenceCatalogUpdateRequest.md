Send-CMAssetIntelligenceCatalogUpdateRequest
--------------------------------------------




### Synopsis
Requests a catalog update for uncategorized software titles.



---


### Description

The Send-CMAssetIntelligenceCatalogUpdateRequest cmdlet requests an update of the Asset Intelligence catalog for software title categorization from System Center Online. You can request an update for catalog items or software categories in the Asset Intelligence catalog.



You can also use the Sync-CMAssetIntelligenceCatalog cmdlet to synchronize the local Asset Intelligence catalog with System Center Online to get the latest software title categorization.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAssetIntelligenceCatalogItem](Get-CMAssetIntelligenceCatalogItem)



* [Sync-CMAssetIntelligenceCatalog](Sync-CMAssetIntelligenceCatalog)





---


### Examples
#### Example 1: Request an update for a software category
```PowerShell
PS XYZ:\> Send-CMAssetIntelligenceCatalogUpdateRequest -Name "Browsers"
```
This command requests an update of the Asset Intelligence catalog for the software category named Browsers.


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



#### **Id**

Specifies an array of IDs of Asset Intelligence catalog items.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |SoftwareKey|



#### **Name**

Specifies an array of names of software categories in the Asset Intelligence catalog.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |CommonName|



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
Send-CMAssetIntelligenceCatalogUpdateRequest [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Send-CMAssetIntelligenceCatalogUpdateRequest [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
