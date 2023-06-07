Get-CMAADTenant
---------------




### Synopsis
Get Azure Active Directory tenant connected with the Configuration Manager site.



---


### Description

Use this cmdlet to get Azure Active Directory tenant connected with the Configuration Manager site.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMCollectionCloudSync](Set-CMCollectionCloudSync)





---


### Examples
#### Example 1: Get all Azure Active Directory tenants connected with the Configuration Manager site
```PowerShell
Get-CMAADTenant
```

#### Example 2: Get an Azure Active Directory tenant with name "Contoso" connected with the Configuration Manager site
```PowerShell
Get-CMAADTenant -Name "Contoso"
```

#### Example 2: Get an Azure Active Directory tenant with Id "72f988bf-00ab-11cd-22ef-2d7cd011db00" connected with the Configuration Manager site
```PowerShell
Get-CMAADTenant -Id "72f988bf-00ab-11cd-22ef-2d7cd011db00"
```



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

Specify the Tenant ID of Azure Active Directory tenant.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |TenantId|



#### **Name**

Specify the Name of Azure Active Directory tenant.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |TenantName|



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
Get-CMAADTenant [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMAADTenant [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
