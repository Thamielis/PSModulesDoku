Remove-CMThirdPartyUpdateCatalog
--------------------------------




### Synopsis
Remove a third-party software updates catalog.



---


### Description

Use this cmdlet to remove a third-party software updates catalog. For more information, see Enable third-party software updates (/mem/configmgr/sum/deploy-use/third-party-software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMThirdPartyUpdateCatalog](Get-CMThirdPartyUpdateCatalog)



* [New-CMThirdPartyUpdateCatalog](New-CMThirdPartyUpdateCatalog)



* [Set-CMThirdPartyUpdateCatalog](Set-CMThirdPartyUpdateCatalog)



* [Publish-CMThirdPartySoftwareUpdateContent](Publish-CMThirdPartySoftwareUpdateContent)



* [Get-CMThirdPartyUpdateCategory](Get-CMThirdPartyUpdateCategory)



* [Set-CMThirdPartyUpdateCategory](Set-CMThirdPartyUpdateCategory)



* [Enable third-party software updates](Enable third-party software updates)





---


### Examples
#### Example 1: Force remove the catalog by name
```PowerShell
Remove-CMThirdPartyUpdateCatalog -Name "Contoso updates catalog" -Force
```

#### Example 2: Remove the catalog as an object
```PowerShell
$catalog = Get-CMThirdPartyUpdateCatalog -Name "Contoso updates catalog"
Remove-CMThirdPartyUpdateCatalog -ThirdPartyUpdateCatalog $catalog
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Force remove the third-party updates catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the third-party updates catalog.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |0       |False        |CatalogId|



#### **InputObject**

Specify an object for the third-party updates catalog. To get this object, use the Get-CMThirdPartyUpdateCatalog (Get-CMThirdPartyUpdateCatalog.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                |
|-----------------|--------|--------|--------------|-----------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|ThirdPartyUpdateCatalog|



#### **Name**

Specify the name of the third-party updates catalog.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |0       |False        |CatalogName|



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMThirdPartyUpdateCatalog [-Id] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMThirdPartyUpdateCatalog [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMThirdPartyUpdateCatalog [[-Name] <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
