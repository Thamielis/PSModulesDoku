Publish-CMThirdPartySoftwareUpdateContent
-----------------------------------------




### Synopsis
Publish third-party software update content



---


### Description

Use this cmdlet to publish third-party software update content. When you publish an update, the binary files are downloaded from the vendor and placed into the `WSUSContent` directory on the top-level software update point. For more information, see Publish and deploy third-party software updates (/mem/configmgr/sum/deploy-use/third-party-software-updates#publish-and-deploy-third-party-software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMThirdPartyUpdateCatalog](Get-CMThirdPartyUpdateCatalog)



* [New-CMThirdPartyUpdateCatalog](New-CMThirdPartyUpdateCatalog)



* [Remove-CMThirdPartyUpdateCatalog](Remove-CMThirdPartyUpdateCatalog)



* [Set-CMThirdPartyUpdateCatalog](Set-CMThirdPartyUpdateCatalog)



* [Get-CMThirdPartyUpdateCategory](Get-CMThirdPartyUpdateCategory)



* [Set-CMThirdPartyUpdateCategory](Set-CMThirdPartyUpdateCategory)



* [Enable third-party software updates](Enable third-party software updates)





---


### Examples
#### Example 1: Get and publish a third-party update
```PowerShell
Get-CMSoftwareUpdate -Name "third-party update" | Publish-CMThirdPartySoftwareUpdateContent
```



---


### Parameters
#### **CIId**

Specify one or more CI_ID s for updates to publish.






|Type       |Required|Position|PipelineInput|Aliases                   |
|-----------|--------|--------|-------------|--------------------------|
|`[Int32[]]`|true    |named   |False        |CI_ID<br/>CIIds<br/>CI_IDs|



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



#### **InputObject**

Specify a software update object for a third-party update to publish. To get this object, use the Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)cmdlet.






|Type               |Required|Position|PipelineInput |Aliases                           |
|-------------------|--------|--------|--------------|----------------------------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|SoftwareUpdate<br/>SoftwareUpdates|



#### **Name**

Specify the name of one or more updates to publish.






|Type        |Required|Position|PipelineInput|Aliases                                                 |
|------------|--------|--------|-------------|--------------------------------------------------------|
|`[String[]]`|true    |named   |False        |LocalizedDisplayName<br/>LocalizedDisplayNames<br/>Names|



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Publish-CMThirdPartySoftwareUpdateContent -CIId <Int32[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMThirdPartySoftwareUpdateContent [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMThirdPartySoftwareUpdateContent [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
